# MRC 22: MOR Staking - A Free Market Mechanism To Direct MOR Rewards Toward Smart Agent & End User Application Builders

## Status: In Progress

## Introduction
As described in the Waterloo paper, builders of Smart Agents and other End User Applications will receive 24% of all MOR emissions.
https://github.com/MorpheusAIs/MRC/blob/main/MRC08.md

These rewards will be directed in proportion to the MOR holders who "Stake" their MOR into the MOR20 Smart Contract for a specific Smart Agent. For purposes of this proposal, those who stake their MOR will be referred to as “Stakers.”

So for example if a MOR holder has 1% of the MOR in circulation and Stakes it toward "DeFiAgent 420 (DA420)", then for as long as that MOR is Staked, the Morpheus protocol will direct 1% of the 24% of MOR emissions (0.24% of all 14,400 daily MOR emissions = 34.56 MOR per day) toward the DeFiAgent 420's AMM Uniswap pool. 

In return MOR Stakers earn the new DA420 tokens in the DeFIAgent project they Staked towards. 

## Value Proposition
**This MOR Staking approach has some compelling benefits:**
- Thus the MOR token will become the common trading pair for the Protocol Owned Liquid of every project launched on Morpheus (like ETH is for projects on Ethereum).
- This effectively extends the model Morpheus has already proven with stETH to MOR as the means of bootstrapping projects on top of its platform.   
- Holders of the MOR token get to individually express which projects they think are most worthy of support.
- Holders of the MOR token gain tokens in projects building on Morpheus without having to sell their MOR. 
- The Morpheus protocol sends all rewards directly to the project & the Stakers and so no central points of failure are created in the new projects.
- The project creates a straightforward path to rewarding Coders and thus attract builders to maintain / expand its Code base.
- Projects get access to Compute (as MOR holders have access to Inference on Morpheus) since the project is holding MOR in the Protocol Owned Liquidity this will poweer their Smart Agent interactions.

## MOR Holders - Additional Benefit
The MOR token is currently planned to grant holders the ability to access inference capabilities on the Morpheus platform. This proposal suggests an additional opportunity to benefit from holding MOR. It is proposed that holders of MOR can stake their MOR tokens to support new and existing Smart Agents and End User Applications leveraging the Morpheus network. In exchange for staking their MOR tokens in support of a Smart Agent or End User Application, Stakers will receive native tokens from the Smart Agent / End User Application.

For MOR holders, the process is as follows:
1) Obtain MOR via buying on the open market or earning via providing Capital, Code, Compute, or contributing to Community.
2) Review listing of available Smart Agents / End User Applications. 
3) Complete research and due diligence on Smart Agents / End User Applications. All staking decisions are at the Staker’s own risk - Morpheus does not review, endorse, or take any responsibility for the Smart Agents / End User Applications.
4) Select Smart Agent / End User Application to stake. 
5) Stake MOR tokens - Staking will lock up MOR tokens for 7 days during which Stakers will be unable to withdraw or interact with MOR tokens.
6) As long as MOR tokens remain staked (and Smart Agent / End User Application is emitting rewards), Stakers will earn native tokens from the Smart Agent / End User Application. The exact process of native token emissions and redemption will be up to the individual Smart Agent / End User Application, however, there will likely be two unique processes: 
- **New Smart Agent / End User Application** - For projects at their genesis, they may look to follow a similar bootstrap period as Morpheus itself did. These will range in duration, but during that time, native tokens will be earned, but not claimable until the completion of the bootstrap period. This will ensure that by the time tokens are claimable, there are enough tokens in circulation and liquidity built up, that an efficient market can develop.
- **Existing Smart Agent / Application** - For projects that are already live and are expanding their existing operations to incorporate Morpheus, they will already have circulating supply and liquidity. Therefore, a bootstrap period is not needed, and tokens will be available for stakers immediately.
7) When Stakers no longer want to support a Smart Agent / End User Application, they will unstake their MOR tokens. This must take place after the 7 day lockup period ends. Once MOR tokens are unstaked, native token rewards will stop. 

The following outline explicitly defines what staking does and does not do:

Staking DOES:
- Lock Stakers’s ability to withdraw staked MOR for 7 days
- Earn Staker native tokens from Smart Agent / End User Application following the details as determined by the particular Smart Agent / End User Application

Staking does NOT:
- Trade holders’s MOR tokens for Smart Agent / End User Application tokens
- Relinquish holders’s ownership of principal MOR
- Transfer relative rights to inference away from Staker

## Smart Agent / End User Applications
At Morpheus’ core is decentralization. Therefore, any Smart Agent / End User Application will be considered eligible for staking. The onus will fall on the individual MOR holders and the community to evaluate Smart Agents / End User Applications. Morpheus takes no responsibility for which Smart Agents / End User Applications are eligible for staking and it is up to everyone to do their own research. 

Any Smart Agent / End User Application wanting to be eligible will do so on-chain. As the smart contracts are developed, additional guidance will be provided with supporting details and required information. Smart Agents / End User Applications are encouraged to publish additional information and interact within the Morpheus community.

With all that said, it is beneficial to provide a framework of standards for Smart Agents / End User Applications looking to participate. While each Smart Agent / End User Application is eligible to add, remove, and adjust any and all terms as they see fit, this proposal is providing guidance and a template as a starting point for those wishing to use it. The following represents some of the information that Smart Agents / End User Applications should consider providing to the community:

- **Name:** Project ABC
- **Team:** Person 1, Person 2, Person 3
- **Website:** Live or test Smart Agent / End User Application
- **Documentation:** GitHub, Whitepaper, etc
- **Socials:** Twitter, Discord, etc
- **Description:** Project ABC is a Smart Agent that supports users looking to do …
- **Audits:** Project ABC was audited by Firm 123 which can be found at www.123.com.

- **Token:** $ABC
- **Token Contract:** 0x000111222333444555666777
- **Circulating Supply:** 21,000,000
- **Max Supply:** 42,000,000
- **Tokens Set Aside for Stakers:** 1,000,000
- **Duration of Staking Program:** 100 Days
- **Staking Program Start Date:** July 1, 2024
- **Staking Program Schedule:** 10,000 $ABC will be distributed pro-rata to MOR stakers for 100 days beginning on July 1, 2024 at 12:00 pm UTC. At the completion of 100 days, Project ABC will determine if another round of staking incentives will be executed, but makes no guarantees that further incentives will be available.
- **Additional Token Notes:** $ABC will be earned block by block and emitted directly to the User's wallet. Tokens are unlocked immediately and available for use.

## MOR Token Emissions
There will be 24% of the total emissions set aside for MOR Staking signaling. This is the same 24% Community Builders Rewards bucket as outlined in the Whitepaper. In order to best utilize these emissions, the goal is to find the appropriate balance between encouraging Smart Agent / End User Application development, while also retaining the value of the MOR token. As such, the 24% of emissions will be distributed in proportion of MOR staked relative to the total circulating supply. Any undistributed emissions will be reserved and held until the completion of Epoch 1 (Year 16). When Epoch 1 ends, the banked emissions will be aggregated and restart the same methodology for Epoch 2 (years 17 - 32).  

The table below provides a more robust numerical example of how this works based on the following hypothetical assumptions:
- Circulating Supply: 16,000 MOR
- Daily Total MOR Emissions: 1,000 MOR
- Daily Staking Emissions Available (24%): 240 MOR

| Staked Project          | Staked MOR | % of Total Circulating Supply | MOR Allocated |
| ----------------------- | ---------- | ----------------------------- | -------------  |
| Smart Agent 1           |    1,000   |              6.25%            | 15.00          |
| Smart Agent 2           |    2,000   |             12.50%            | 30.00          |
| Front End Application A |      500   |              3.13%            | 7.50           |
| Front End Application B |    2,500   |             15.63%            | 37.50          |
| None                    |   10,000   |             62.50%            | 150.00         |
| Total                   |   16,000   |            100.00%            | 240.00         |

This approach ensures that there is access for Smart Agents / End User Applications to get ample emissions and support new development. At the same time, this approach will ensure that no Smart Agents / End User Applications are provided outsized emissions. Especially in the early days, there may be a limited number of Smart Agents / End User Applications for holders to choose to stake. This approach helps to avoid a situation where, for example, if there was only one Smart Agent available, and only 2% of total MOR was staked, that Smart Agent would only get 0.48% of emissions (2% of 24%) instead of getting the entire 24%.

Note: Circulating Supply is defined as the total amount of MOR that has been emitted since inception, including MOR that is accrued but not yet distributed. For example, on Day 90, circulating supply will be 1,286,112 MOR (Capital + Code + Compute + Community + Protection Fund) even though Compute and Community MOR has not yet been distributed. This also means that any MOR in the Protection Fund or protocol-owned liquidity (PoL) is included in circulating supply. The net impact of this is that there will never be 100% of circulating supply staked (since there will always be some percent of MOR in the Protection Fund and PoL). This ensures that there will be MOR at the end of Epoch 1 and available to fund the staking for Epoch 2.

## Process for MOR Emissions + Accrued MOR
MOR emissions will be allocated on a block by block basis to the Smart Agent / End User Application AMM Uniswap Pool. 50% of the emitted MOR will be swapped for the Smart Agent / End User Application’s native token. The total amount will then be added as protocol-owned liquidity, encompassing the full range within the AMM Uniswap Pool.

Since Community emissions have been accruing since launch, but not distributed, there will be an accrual of MOR as of the date that Community rewards begin distribution. While no specific date has been identified, the following provides some estimates to understand the potential size of this accrual:

| Day | Accrued Community MOR For Staking |
| --- | --------------------- |
| 90  | 308,667   | 
| 120 | 410,489   |
| 150 | 511,778   |  
| 180 | 612,534   |  
| 210 | 712,756   |
| 240 | 812,445   |
| 270 | 911,601   |

On the date that Community rewards go-live, the accrued MOR emissions for Staking will be added to the pool of Staking emissions over the next 360 days on a linear basis. For example, if Community rewards go-live on Day 240, the accrued 812,445 MOR for Staking will be distributed daily via an extra 3,385 MOR available to Smart Agents / End User Applications. This provides an extra incentive to early Smart Agents / End User Applications. 

Note: The same methodology as used for pro-rata emissions (Staked MOR divided by total circulating supply) will apply to the Accrued emissions as well. Using the same example, if on Day 240 only 25% of total MOR supply is staked, then 846 of the 3,385 MOR will be distributed, with the remaining 2,539 MOR being reserved until Epoch 2.

## Implementation
The implementation would be a variation of the standard MOR20 Token Smart Contracts, but instead of stETH being the source of yield, the MOR token itself would serve this purpose.

All other aspects of the MOR20 Smart Contracts would be the same. The same AMM pool model. The same weights system to track and reward Capital Providers, Coders, Compute and so forth.

This would be a phase 3 Smart Contract deployment after Code, Capital, and Compute are all live on Morpheus as part of the Community App Builder phase.
