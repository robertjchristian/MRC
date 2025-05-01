# Specification: MOR Subnet Namespace Smart Contract

## 1. Overview

The **MOR Subnet Namespace** is a decentralized system for registering and managing unique subnet names on the Ethereum blockchain. It enables subnets (e.g., decentralized networks, blockchain layers, or applications) to claim human-readable names (e.g., `mysubnet.mor`) and associate them with metadata, such as an Ethereum address, IPFS hash, or other relevant data. The MOR system is inspired by the **Ethereum Name Service (ENS)** but is tailored for subnet-specific use cases.

### Goals
- Provide a secure, decentralized, and transparent mechanism for registering unique subnet names.
- Ensure names are globally unique and resolvable to associated metadata.
- Support extensible metadata for subnet-specific needs.
- Minimize gas costs for registration and management.
- Enable transferability and expiration of name ownership.

### Key Features
- **Unique Name Registration**: Subnets can register a unique name under the `.mor` top-level domain.
- **Ownership and Transfer**: Names are owned by Ethereum addresses, with support for transferring ownership.
- **Expiration and Renewal**: Names are leased for a defined period and can be renewed.
- **Resolver System**: Names can resolve to Ethereum addresses, content hashes, or custom metadata.
- **Subdomain Support**: Owners can create subdomains (e.g., `sub.mysubnet.mor`).
- **Gas Efficiency**: Optimized for low-cost interactions on Ethereum.

## 2. Architecture

The MOR Subnet Namespace system consists of the following core components:

### 2.1. MOR Subnet Registry
The **MOR Subnet Registry** is the smart contract that maintains a mapping of names to their owners and associated metadata. It is the single source of truth for name ownership and resolver information.

- **Data Structure**:
  - Maps a `keccak256` hash of the name (e.g., `keccak256("mysubnet.mor")`) to a record containing:
    - `owner`: The Ethereum address that owns the name.
    - `resolver`: The address of the resolver contract (if any).
    - `ttl`: Time-to-live (expiration timestamp) for the name lease.
    - `createdAt`: Timestamp of registration.
    - `metadata`: Optional metadata (e.g., IPFS hash for subnet details).

- **Functions**:
  - `register(bytes32 node, address owner, uint256 duration)`: Registers a name for a specified duration.
  - `setOwner(bytes32 node, address newOwner)`: Transfers ownership of a name.
  - `setResolver(bytes32 node, address resolver)`: Sets the resolver contract for a name.
  - `renew(bytes32 node, uint256 duration)`: Extends the lease duration of a name.
  - `reclaim(bytes32 node)`: Allows the owner to reclaim an expired name.
  - `getRecord(bytes32 node)`: Retrieves the record for a name.

### 2.2. Resolver
The **Resolver** is a contract that resolves a name to specific resources (e.g., an Ethereum address, IPFS hash, or custom data). Each name can have its own resolver contract, or use a default public resolver provided by the MOR Subnet Namespace.

- **Standard Resolver Interface** (inspired by ENS Resolver):
  ```solidity
  interface IResolver {
      function addr(bytes32 node) external view returns (address);
      function contentHash(bytes32 node) external view returns (bytes memory);
      function setAddr(bytes32 node, address addr) external;
      function setContentHash(bytes32 node, bytes memory hash) external;
      function supportsInterface(bytes4 interfaceID) external view returns (bool);
  }

  ### Extensibility
Subnets can deploy custom resolvers to support additional data types (e.g., URLs, subnet configurations, or other metadata).

## 2.3. Registrar
The **Registrar** is a contract responsible for handling the registration and renewal process for names under the `.mor` domain. It enforces rules such as name availability, pricing, and lease duration.

### Key Features
- Ensures names are unique and not already registered.
- Implements a pricing model (e.g., based on name length or fixed fees).
- Manages lease durations (e.g., 1 year minimum, renewable).
- Supports auctions or first-come-first-serve registration.

### Functions
- `registerName(string memory name, address owner, uint256 duration)`: Registers a name under `.mor`.
- `renewName(string memory name, uint256 duration)`: Renews a name’s lease.
- `price(string memory name, uint256 duration)`: Returns the registration cost.
- `available(string memory name)`: Checks if a name is available.

## 2.4. Subdomain Support
The mor system supports hierarchical names (subdomains). Owners of a name (e.g., `mysubnet.mor`) can create subdomains (e.g., `node.mysubnet.mor`) and assign ownership or resolvers to them.

### Subdomain Registry
- Extends the mor Registry with a function to create subdomains:
  ```solidity
  function setSubnodeOwner(bytes32 node, bytes32 label, address owner) external;

  - `node` is the parent name’s hash (e.g., `keccak256("mysubnet.mor")`).
- `label` is the subdomain’s hash (e.g., `keccak256("node")`).

## 3. Smart Contract Specification
Below is a simplified implementation of the core mor Registry contract, written in Solidity.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract morRegistry {
    struct Record {
        address owner;
        address resolver;
        uint64 ttl;
        uint64 createdAt;
    }

    mapping(bytes32 => Record) public records;
    address public registrar;

    event NameRegistered(bytes32 indexed node, address owner, uint64 ttl);
    event NameTransferred(bytes32 indexed node, address newOwner);
    event ResolverUpdated(bytes32 indexed node, address resolver);

    modifier onlyOwner(bytes32 node) {
        require(records[node].owner == msg.sender, "Not owner");
        _;
    }

    modifier onlyRegistrar() {
        require(msg.sender == registrar, "Not registrar");
        _;
    }

    constructor(address _registrar) {
        registrar = _registrar;
    }

    function register(bytes32 node, address owner, uint64 duration) external onlyRegistrar {
        require(records[node].owner == address(0) || records[node].ttl < block.timestamp, "Name already registered");
        records[node] = Record({
            owner: owner,
            resolver: address(0),
            ttl: uint64(block.timestamp) + duration,
            createdAt: uint64(block.timestamp)
        });
        emit NameRegistered(node, owner, duration);
    }

    function setOwner(bytes32 node, address newOwner) external onlyOwner(node) {
        records[node].owner = newOwner;
        emit NameTransferred(node, newOwner);
    }

    function setResolver(bytes32 node, address resolver) external onlyOwner(node) {
        records[node].resolver = resolver;
        emit ResolverUpdated(node, resolver);
    }

    function renew(bytes32 node, uint64 duration) external onlyRegistrar {
        require(records[node].ttl >= block.timestamp, "Name expired");
        records[node].ttl += duration;
        emit NameRegistered(node, records[node].owner, duration);
    }

    function getRecord(bytes32 node) external view returns (Record memory) {
        return records[node];
    }
}
### Key Notes on Implementation
- **Security**: The contract uses `onlyOwner` and `onlyRegistrar` modifiers to restrict access to sensitive functions.
- **Gas Optimization**: The `Record` struct is packed efficiently to minimize storage costs.
- **Extensibility**: The registry supports custom resolvers and metadata via the `resolver` field.
- **Event Logging**: Events are emitted for all state changes to ensure transparency and auditability.

## 4. Registration Process
The process for registering a subnet name is as follows:

4A. **Check Availability**:
   - The user queries the Registrar contract’s `available` function to verify that the desired name (e.g., `mysubnet.mor`) is not already registered or reserved.

4B. **Calculate Cost**:
   - The user calls the `price` function to determine the registration cost, which may depend on name length, demand, or duration.

4C. **Register Name**:
   - The user submits a transaction to the Registrar contract’s `registerName` function, specifying:
     - The name (e.g., `mysubnet.mor`).
     - The owner’s Ethereum address.
     - The lease duration (e.g., 1 year in seconds).
     - Payment (in ETH) for the registration fee.
   - The Registrar computes the `keccak256` hash of the name and interacts with the mor Registry to create a record.

4D. **Set Resolver**:
   - The owner calls the Registry’s `setResolver` function to assign a resolver contract for the name.
   - The resolver is configured with metadata (e.g., an Ethereum address or IPFS hash).

5. **Resolve Name**:
   - Anyone can query the resolver to retrieve the associated metadata (e.g., `resolver.addr(keccak256("mysubnet.mor"))`).

## 5. Standards and Interoperability
The mor system adheres to Ethereum standards to ensure compatibility and interoperability:

- **EIP-137 (ENS)**: The mor Registry and Resolver are inspired by ENS’s architecture and interface.
- **EIP-181**: Name normalization follows ENS’s rules (e.g., lowercase, no special characters).
- **EIP-165 (Interface Detection)**: Resolvers implement `supportsInterface` to advertise supported features.
- **EIP-712 (Typed Data Signing)**: Optional support for off-chain registration signatures to reduce gas costs.

### Name Normalization
- Names must be lowercase and alphanumeric (e.g., `mysubnet.mor`).
- Invalid characters (e.g., spaces, uppercase) are rejected by the Registrar.
- Minimum name length: 3 characters (excluding `.mor`).
- Maximum name length: 255 characters (including `.mor`).

## 6. Pricing and Economics
- **Registration Fee**: Determined by the Registrar, potentially based on:
  - Name length (e.g., shorter names are more expensive).
  - Fixed fee per year of lease duration.
  - Market demand (e.g., auction for premium names).
- **Renewal Fee**: Similar to registration, but typically lower to incentivize renewals.
- **Revenue**: Fees are collected by the Registrar and may be:
  - Burned (to reduce ETH supply).
  - Sent to a treasury for mor system maintenance.
  - Distributed to stakers or governance (if applicable).

## 7. Security Considerations
- **Front-Running**: Mitigated by requiring a commit-reveal scheme for high-demand names or auctions.
- **Reentrancy**: All state changes follow the Checks-Effects-Interactions pattern.
- **Name Squatting**: Mitigated by lease expirations and renewal incentives.
- **Access Control**: Only the owner or Registrar can modify critical data.
- **Upgradeability**: The Registry can be made upgradeable via a proxy pattern, with governance approval.

## 8. Example Usage

### Registering a Name
```solidity
// User wants to register "mysubnet.mor" for 1 year
Registrar registrar = Registrar(0x...);
string memory name = "mysubnet";
uint256 duration = 365 days;

// Check availability
require(registrar.available(name), "Name not available");

// Calculate cost
uint256 cost = registrar.price(name, duration);

// Register name
registrar.registerName{value: cost}(name, msg.sender, duration);

### Resolving a Name
```solidity
morRegistry registry = morRegistry(0x...);
bytes32 node = keccak256(abi.encodePacked("mysubnet.mor"));

// Get resolver
address resolverAddr = registry.getRecord(node).resolver;
IResolver resolver = IResolver(resolverAddr);

// Resolve to address
address subnetAddr = resolver.addr(node);

## 9. Future Extensions
- **Governance**: Introduce a DAO to manage Registrar policies (e.g., pricing, reserved names).
- **Multi-Chain Support**: Extend mor to Layer 2 solutions or other EVM-compatible chains.
- **Premium Names**: Implement auctions for high-value names (e.g., `node.mor`, `chain.mor`).
- **Integration with DeFi**: Allow names to be used as collateral or in NFT marketplaces.
- **Off-Chain Resolution**: Support DNS-like resolution for broader adoption.

## 10. Conclusion
The MOR Subnet Namespace (.MOR extension) provides a robust, decentralized solution for registering unique subnet names on Ethereum, drawing heavily from the ENS standard. By combining a simple registry, flexible resolvers, and a modular registrar, MOR Subnet names enables subnets to establish a recognizable identity on the blockchain while maintaining security, extensibility, and interoperability.

This specification can be implemented as a starting point and extended based on specific subnet requirements or community governance.
