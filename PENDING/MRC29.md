## Morpheus MRC29: Launch TCM for MOR Yield Farming on Solana with JitoSOL
**by Macro, April 1, 2024**
  
> NOTE: this MRC is the merge of MRCs [13](https://github.com/antonbosss/MRC/blob/main/PENDING/MRC13.md) and [17](https://github.com/antonbosss/MRC/blob/main/PENDING/MRC17.md), made previously. For background context, please reference them here respectively.`

---

## Status
**April 1, 2024: PENDING**

**Comments:**  

---

## Objective
This MRC extends the existing MRC 13 and MRC 17 write ups to include a more detailed technical approach to the implementation. The objective of this MRC remains the same: grow Morpheus community and reach by enabling capital farming of MOR on Solana using JitoSOL as the deposit asset, similar to how stETH is used on Ethereum as the deposit asset.

## High Level Requirements
1. Layer Zero is the desired interoperability solution for bridging MOR to and from Solana. Requires completion of MOR token contract upgrade to use Layer Zero’s OFT standard (currently under audit by Open Zeppelin). Layer Zero is targeting support for Solana interoperability in May (subject to change). 
2. The Morpheus smart contracts must be upgraded to support multiple yield types. 
3. All MOR is minted on Arbitrum and then bridged over to Solana to reward JitoSOL depositors. 
4. MOR rewards take into account all supported deposit assets (stETH and JitoSOL). 
5. The JitoSOL yield is given to Morpheus while deposited in exchange for MOR yield. Depositors can withdraw their JitoSOL anytime after 7 days from initial deposit. Upon doing so they get their JitoSOL yield back, and stop earning MOR yield in proportion to what they withdraw. 
6. The AMM on Solana will be a SOL : MOR pool on Jupiter, or another AMM which is TBD. This is an open question of which AMM to use, as outlined below. 
7. JitoSOL yield will be converted into SOL so that there is deeper liquidity in the AMM pool. An example of this can be found by looking at the Morpheus Smart Contracts updated to convert wstETH to wETH so the pair on Arbitrum can be wETH / MOR (deeper liquidity, similar objective): https://github.com/MorpheusAIs/SmartContracts/pull/26.
8. The smart contracts for this MRC when finished will be deployed to Solana using the Morpheus multi-sig.

## Remaining Open Questions Specific to MRC 29
1. How will the common denomination for multiple yield types work?  
We are suggesting ETH as the common denominator due to it being the deepest DeFi liquidity asset.

2. What oracle will be used for common denomination pricing in ETH for sake of calculating MOR yield reward amounts? For example, the amount of JitoSOL deposited must be represented in ETH format so that it’s the same denomination as the stETH deposited on Ethereum
2.1. Sub-question: Should this be denominated in stETH (in case of depeg from ETH)?

3. How will block time be treated by Layer Zero in their implementation? Will need a common blocktime in addition to a common denominator mentioned above so that rewards can be calculated at a consistent interval. Initial discussion is to use the slower of the chain’s blocktimes (ETH). However, one additional sub question has emerged:
3.1. Sub-question: On Solana blocktimes can be unreliable. Slot times are more reliable. How will that be taken into account to arrive at a consistent time for yield reward snapshots?

4. What AMM should have the SOL : MOR pair? Jupiter?

5. How exactly do we create the pool on Jupiter if that is the chosen AMM? What is the best way to convert JitoSOL to SOL?

6. Are there differences in the implementation in terms of how you give up JitoSOL yield compared to how you give up stETH yield?

## Potential Dependencies
1. What is the status update of the Open Zeppelin audit of the Layer Zero OFT standard for the MOR token contract?
2. What is the update and who should we talk about about the "in design" status on the supporting multiple yield types for the existing Morpheus contracts?
3. Can Morpheus contributors start a signal group with us and Layer Zero and us so we can coordinate with them on the outstanding blocktime question? We would like to get their thoughts on the work around for this (think Slots are more consistent / reliable than blocktimes on Solana).
