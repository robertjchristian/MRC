# MRC 22: MOR Staking - A Free Market Mechanism To Direct MOR Rewards Toward End User Applications
As described in the Waterloo paper, builders of Smart Agents and other End User Applications will receive 8% of all MOR emissions.
https://github.com/MorpheusAIs/MRC/blob/main/MRC08.md

These rewards will be directed in proportion to the MOR holders who "Stake" their MOR into the MOR20 Smart Contract for a specific Smart Agent.

So for example if a MOR holder has 1% of the MOR in circulation and Stakes it toward "DeFiAgent 420 (DA420)", then for as long as that MOR is Staked, the Morpheus protocol will direct 1% of the 8% of MOR emissions (0.08% of all 14,400 daily MOR emissions = 11.52 MOR per day) toward the DeFiAgent 420's AMM Uniswap pool. 

In return MOR Stakers earn the new DA420 tokens in the DeFIAgent project they Staked towards. 

**This MOR Staking approach has some compelling benefits:**
- Thus the MOR token will become the common trading pair for the Protocol Owned Liquid of every project launched on Morpheus (like ETH is for projects on Ethereum).
- This effectively extends the model Morpheus has already proven with stETH to MOR as the means of bootstrapping projects on top of its platform.   
- Holders of the MOR token get to individually express which projects they think are most worthy of support.
- Holders of hte MOR token gain tokens in projects building on Morpheus without having to sell their MOR. 
- The Morpheus protocol sends all rewards directly to the project & the Stakers and so no central points of failure are created in the new projects.
- The project creates a straight forward path to rewarding Coders and thus attract builers to maintain / expand its Code base.
- Projects get access to Compute (as MOR holders have access to Inference on Morpheus) since the project is holding MOR in the Protocol Owned Liquidity this will poweer their Smart Agent interactions.

## Implementation
The implementation would be a variation of the standard MOR20 Token Smart Contracts, but instead of stETH being the source of yield, the MOR token itself would serve this purpose.

All other aspects of the MOR20 Smart Contracts would be the same. The same AMM pool model. The same weights system to track and reward Capital Providers, Coders, Compute and so forth.

This would be a phase 3 Smart Contract deployment after Code, Capital, and Compute are all live on Morpheus as part of the Community App Builder phase.
