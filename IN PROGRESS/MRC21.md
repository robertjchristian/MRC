## MRC21: Non Fungible Agents

---

## Status
**April 1st, 2024: IN PROGRESS**

--- 

### Simple Summary
The non-fungible agent is the decentralized operating entity that combines autonomous artificial intelligence and blockchain technologies into something easily understood by non-technical people.


### Abstract
As a way of identifying, understanding, owning, transacting with, and securing Smart Agents using the unique features of the blockchain, there is no need to reinvent the NFT wheel. The MOR21 Non-Fungible Agent (NFA) is a technical framework, defining a set of rules and interfaces for creating and managing unique smart agents in the Morpheus ecosystem.

The MOR21 smart contract adopts and evolves key interfaces from the ERC smart contract to the agent toolkit.

#### Smart Agent Diagram

![NFA smart agent - NFAs](https://github.com/MorpheusAIs/MRC/assets/76454555/a1b0a131-d021-4301-a94c-c486e93c9be8)

## Motivation
#### A universe of specialized agents
As autonomous computing becomes a key focus of the Morpheus ecosystem, this MRC looks to define the first guardrails as a set of needs.  A person or agent needs transactional confidence that an agent is unaltered and easy to understand.
1. There is a need to ensure that the link to Smart Rank data built into each Smart Agent remains non-fungible, allowing for increasing precision.
2. There is a need to be confident that the Smart Agent code that was initially submitted to the Morpheus ecosystem hasn’t been altered.
3. There is a need to define the limits of a Smart Agent’s toolset by being able to review and compare the original code in human readable format. 
4. There is a need to provide a “usage manual” in the form of an ABI that defines an agent’s prerequisites, data types for I/O, and expected deliverables
5. There needs to be a means for any smart agent type to be packaged independently of the tech stack required to create and maintain the smart agent.  Anyone who can build any type of agent can package it as an NFA.

#### Use cases
We considered use cases where the Smart Agent performs data labor as a fee-based service.  Fees for services are charged and collected by the agent when the purchased service is delivered. It is foreseen that Smart Agents will be highly specialized to keep development and network fees low for the developer.


> Example:  Tax Preparation for Swiss Dental Practices Smart Agent

> A developer writes an agent that does taxes for dentists practicing in Switzerland. The agent may charge 1000 MOR for the first year’s return and 500 MOR for each subsequent year’s return. That Swiss tax preparing smart agent's portfolio of dentists would partially define the value of that agent for the agent owner. If after a few years and a handful of repeat Swiss dentist customers, the agent would represent a market cap and the owner could sell the agent along with the agent’s customer base. This is the exact same way a service business is sold today. So, An NFA is similar to a stand-alone service business that is verified onchain.

#### Actors in the NFA universe
Not coincidentally, this aligns with the reward structure created by the Morpheus White Paper.  The NFA can be seen as a Morpheus Microcosm that can live anywhere and still serve the project’s aspirations. 

The NFA is considered by:
1. Developers who write and publish agents to perform paid data labor, creating a front-end in a community. 
2. Compute providers who may choose to host agents’ endpoints as a means of selling compute in the form of existing, “normal” services
3. Front end marketplaces that look to broker the sale of agents, agent tools, and supporting agent services, like smart agent chaining

### Functionality

#### Requirements
 - EIP 721 (https://eips.ethereum.org/EIPS/eip-721)
 - EIP 165 (https://eips.ethereum.org/EIPS/eip-165)
 - EIP 214 (https://eips.ethereum.org/EIPS/eip-214)

We start with the functionality outlined in ERC 721 (https://eips.ethereum.org/EIPS/eip-721). Current 721 functions:
 - Chain location / Addressing
 - Cost to purchase 
 - Ownership
 - rovenance 
 - Royalties 
 - Key ERC-721 Components:
   - tokenId: A unique identifier for each NFT.
   - owner: The Ethereum address that currently owns the NFT.
   - balanceOf: Returns the number of NFTs owned by a given address.
   - transfer: Allows the current owner of an NFT to transfer it to another address.
   - approve: Allows the owner of an NFT to give permission for someone else to transfer it on their behalf.
   - allowance: Returns the number of NFTs that a third party can transfer for a given owner.
   - safeTransferFrom: Allows the transfer of an NFT with additional safety checks.
   - safeTransferFrom with data: Allows the transfer of an NFT with additional data.
   - tokenURI: Returns the metadata URI for an NFT, which typically includes information like the NFT’s name, description, and image.
   - onERC721Received: Implemented by the recipient contract to receive ERC-721 tokens.
   - approveForAll: Allows the owner of an NFT to approve a third party to transfer all their NFTs.
   - isApprovedForAll: Checks if a third party is approved to transfer all NFTs for a given owner.
Some of the above can/should be refined as omissions or modifications.  

### New functions to be developed
Starting with the refined 721 list above, we add smart-agent-specific functionality, including: 
 - Location
 - I/O 
 - Sale of service
 - Staking
 - Agent Abi
   - Services menu
   - How to engage
   - Language and environmental needs
   - Function manifest
   - System prompting
   - Model requirements
   - Diagnostics and calibration 

A Non-fungible agent has an Agentic ABI, providing a functional interface to the agent, with a minimum weights and model requirement.  

#### Testing benchmarks
A Non-Fungible Agent must include performance metrics at the time of publication to chain.  Users who engage an agent can calibrate for accuracy and fidelity to test a Smart Agent’s use of inference.

#### Trackable Ownership
Expanding on ownership of NFTs each Smart Agent is assigned an Agent Identification Number and linked to is owner through the use of the ownerOf function 

### Smart Agent Tokenomics
NFAs exist to participate in any number of economic situations while remaining decentralized, even if all parties involved with a particular agent are centralized entities.  

#### Mitigating Staking
To mitigate against malicious usage, the agent creator stakes MOR as part of launching an MFA that is accessible to others.  The amount of MOR required a proportional amount to the cost of the Smart Agent’s scope and service costs.  This makes it ultimately unprofitable to create malicious agents.

#### Ownership and Revenue
NFAs generate revenue by performing data services.
Agents can be bought and sold in a marketplace, similar to a non-fungible token.  A multisig-type ownership function allows for fee and license distribution amongst multiple parties. Fees are collected based on the amount of inference used, the computer used, and the, complexity of tasks performed.  Agents can be made available to accomplish remote tasks in exchange for MOR.  Availability can be exclusive or open, providing immutable access rights.

#### Burned Gas and Network Fees
Fees incurred that would normally be used to pay miners, minters, and nodes get burned by the MOR capital contract, adding to the long-term emission value.  Revenue from the NFA services replaces this reward, maintaining decentralization. 

#### Security
The NFA forces the agent being considered to reveal all underlying code and dependencies on chain.  Otherwise a developer could modify an existing agent with malware. 

### Corresponding Front Ends
#### Agent UIUX
Built into any app, site, IOT device, the UIUX that allows for a human or agent interaction with an NFA is considered an agent UIUX.  The most common form today would be chat.

#### NFA Marketplaces
Similar to how an NFA is an evolution of the NFT, a P2P marketplace that is used to buy and sell NFAs is akin to an evolution of the Open Sea Marketplace.  Equally decentralized, anyone can create a marketplace for NFAs. 

A template marketplace is made available along with this specification so that there is no one single Morpheus Smart Agent marketplace.


 

