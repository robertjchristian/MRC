# Toward MOR Interoperability 

## Introduction
To set the stage, MOR is currently instantiated as an ERC20 on Arbitrum. The coin exists, however is unmoveable/untradable until May 8th 2024. 

## Goal
MOR to be omnichain to whatever degree it makes sense. At minimum, we want it to exist seamlessly on Arbitrum & ETH L1. 
Before May 8th 2024 to modify/upgrade/change the Smart Contract is easier. After that date it's obviously messier. Thus this topic should be considered / then implemented before May 8th 2024.

## Evaluation
Many of the open source Smart Contract developers have evaluated LayerZero's OFT paradigm for use in the Morpheus Smart Contracts. 
In particular, they liked: 
- 1) the immutability/non-upgradability of the contracts, and 
- 2) the gas abstraction for better UX.
- 3) The oracle function that can help denominate all yield contributions to Morpheus via ETH price.

Whilte Morpheus is not exclusive to any chain or project, Layer Zero seems to be a good startig point to increase the Interoperability of the MOR token and broaden types of yield contribution.

## Implementation
To start sending tokens from arbitrum to other chains, developers need to do is: 
- 1. Deploy the OFT Adapter contract which works like a lockbox on the source chain, 
- 2. Deploy the OFT contract on each new chain which will become the canonical MOR tokens for those new chains.

## Technical Documentation Details
Link to Layer Zero Docs: https://docs.layerzero.network/contracts/oft-adapter
