# [MRC 13: Launch TCM for MOR Yield Farming on Solana with JitoSOL and/or mSOL](https://www.notion.so/34a6db212f184f59aab47c74cf94f10f?pvs=21)

by Macro, February 26, 2024

## April 1st 2024: Moving this MRC13 into PENDING status. 

Thanks for the good discussion. Love the idea of adding more yield types and Solana to the mix but a series of technical dependencies need to be completed first.

1. The Smart Contracts have to be deployed on Solana (now that the Layer Zero integration is now).
This has to come after late May when the rumored Solana integration with Layer Zero takes place.

2. The Smart Contracts have to be extended to calculate MOR rewards for multiple yield types.

3. Finally the yield provided has to be converted into wETH to be contributed to the Uniswap pool.

Lastly this proposal lacks a weights bid and needs to be more narrow and specific about the work to be done.

**Objective**

Grow Morpheus community and reach by enabling capital farming of MOR on Solana using native Solana LSTs (Liquid Staking Tokens). 

**Summary**

The TCM is a unique fair launch fundraising mechanism that been successfully deployed by Morpheus to farm the MOR token. 

For a breakdown of how the TCM works from a high level please see this write up: https://github.com/MorpheusAIs/TCM

This proposal is to re-write the TCM smart contracts that were implemented for MOR yield farming (on Arbitrum) by depositing stETH (on Ethereum) and deploy them to Solana so that network participants in the Solana ecosystem can participate in MOR farming by contributing capital. 

To the best of our knowledge, the developer platform features mentioned in the above link have not yet been implemented on Ethereum / Arbitrum. Once the platform features have been implemented, we plan to submit another MRC to re-write them on Solana as well.

**Background**

Morpheus has used a novel fair launch fundraising strategy for raising capital. 

By allowing participants to deposit a Liquid Staking token (stETH) and give up the native ETH yield that the LST earns, those participants can farm the native MOR token for the Morpheus project. 

Anyone can participate, hence the fair launch, and participants don’t have to sell their stETH to earn MOR. They just give their yield to Morpheus while it’s deposited. If the participant withdrawals their stETH they will stop earning MOR and will resume earning the native ETH yield. 

The stETH yield that belongs to Morpheus after a participant deposits stETH will be used to provide liquidity in the ETH / MOR AMM pool when the MOR token goes live on May 8, 2024. 

The TCM is a novel way to bootstrap having sufficient on-chain liquidity upon launch of the MOR token without giving away pre-mine allocations to market makers and other capital providers such as VCs (defeats the purpose of the fair launch). 

The Morpheus stETH deposit contract on Ethereum has surpassed $300M deposited demonstrating strong demand for this type of fair launch. The success of the TCM has helped Morpheus expand its community of active participants as there are a lot of stETH depositors who are incentive aligned to see Morpheus do well. 

**Goals**

The goal of this MRC is to expand the community and reach to the Solana ecosystem to allow for farming MOR through the TCM fair launch technique. Solana participants will be able to provide capital in native LST tokens on Solana. 

**Technical Plan**

- Reimplement the staking contracts as a Solana program.
- Use Wormhole to either:
    - Implement a Solana MOR contract and allow token bridging between Solana and Ethereum, or
    - Accept an EVM address as input + communicate staking events back to Ethereum.

**Open Questions**

- Which bridging approach does the Morpheus approach prefer? A list of requirements will help determine the best path. To implement the staking contracts on Solana, we would need a way to bridge/track/mint/etc MOR as rewards.
- Should we integrate with JitoSOL (Jito Labs) or mSOL (Marinade Finance) or both? This is an implantation detail we would love to get feedback from the Morpheus community on.
- Will we want to add developer platform TCM features? Question based on the documentation summarized below: https://github.com/MorpheusAIs/TCM
