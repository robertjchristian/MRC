# MRC17: Adding Solana Yield & MOR Token Proposal

## Introduction
We propose capital contribution integration for Morpheus with the Solana blockchain, aimed at significantly enhancing the liquidity of Morpheus AI's capital providers pool. By leveraging Solana's high-performance capabilities and developing a bespoke smart contract, we aim to introduce SOL staking and contributing staked SOL yield in exchange for MOR tokens. Furthermore, Solana's low transaction fees and high throughput offer a compelling case for it to be a suitable platform for Morpheus, potentially providing an efficient and cost-effective environment for users and the ecosystem at large.

## Implementation
We propose to develop a smart contract on the Solana blockchain that allows users to directly stake SOL in exchange for MOR token rewards. This integration will enable Morpheus AI to access Solana's liquidity and user base, providing a new avenue for growth and capital.

## Smart Contract Development
1) Direct SOL Staking: Users can stake SOL directly via the developed smart contract, with a guaranteed 1:1 return upon redemption.
2) Conversion to JitoSOL: The contract will automatically convert staked SOL into JitoSOL, enabling the protocol to earn staking rewards from the Jito Network.
3) Reward Mechanism: Accrued SOL rewards will be sold daily and added to the Protocol-owned Liquidity (POL) on Morpheus
4) Locking Mechanism for withdrawal: There will be a standard 7-day lock-in for the SOL contributed

## Oracle Use
For the allocation of MOR rewards, an oracle will capture daily Solana market data at a specific time (e.g., 5 PM UTC), ensuring fair and transparent distribution. This process will meticulously be recorded on the Ethereum blockchain by Morpheus contracts, reinforcing the integrity and auditability of the reward mechanism within the ecosystem. This approach underscores the commitment to fairness, leveraging blockchain's transparency to benefit all ecosystem participants.

## Reward Allocation Strategy
In order to have fair and equitable reward distribution to SOL stakers, we plan to utilize the oracle price data to calculate the USD value of SOL and yield contribution. The rewards for SOL stakers will be calculated on a pro-rata basis taking the st-ETH and other capital contribution into account.
     
## Bridging and Distribution
Bridging and distribution for MOR rewards to SOL stakers involves using cross-chain technology like Wormhole. This process allows the transfer of MOR tokens from the Ethereum blockchain to Solana, where they're wrapped. The solana smart contract receives the equivalent MOR reward tokens and distributes among users based on their capital contribution.
To enhance security and governance in the process of bridging and distributing MOR rewards, a multisignature wallet approach will be utilized (this can be a Safe multisig wallet on Ethereum and a Squads mulitisg wallet on the Solana end). This method involves requiring multiple signatures from designated members of the Morpheus AI team or community before any transactions can be approved and executed.

## Wrapped MOR Distribution
Solana stakers will receive wrapped MOR tokens, maintaining a 1:1 value equivalence with MOR on the Ethereum chain, facilitated by cross-chain solutions like Wormhole. Distribution involves converting MOR tokens into a wrapped Solana-compatible format, allowing them to be easily transferred and used within the Solana ecosystem.
Benefits:
- 1) Enhanced Liquidity: The integration significantly increases liquidity, attracting more
capital contribution to Morpheus AI.
- 2) Market Expansion: JtoSol has more than $1bn TVL and should be able to access a
decent portion of it for Morpheus. Accessing Solana's user base also opens new
markets and opportunities for growth.
- 3) Innovative Ecosystem: This partnership exemplifies blockchain interoperability,
showcasing a commitment to innovation and user benefits.
- 4) Affordable Transactions with Solana: Solana stands out in the market for its
exceptionally low transaction fees paired with rapid processing speeds. This makes it an ideal blockchain for Morpheus to integrate with. The combination of affordability and efficiency ensures high transaction volumes and consistent liquidity flow.

![Flow Diagram Overview](https://github.com/MorpheusAIs/MRC/assets/1563345/f17c4122-3c0b-4bd2-a50b-05fc523e5eb2)

