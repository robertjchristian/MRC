# MRC46: 90 Day Delay on MOR Claims for Capital Contributors 

**Status: In Discussion**

**Discord Thread:** https://discord.com/channels/1151741790408429580/1283805259730255884

## Smart Contract Function To Be Added
Add a new variable by updating the smart contract. 
claimLockPeriodAfterStake 

It will be set every time the user deposits, will be counted as current time + 90 days (or other value that can be changed on the contract).

## Purpose
To prevent farmers from depositing stETH and immediately claiming / dumping the MOR tokens earned as there is currently no MOR claim delay function.

Those depositing stETH over a longer period of time are adding value to the Protocol Owned Liquidity.
Those only depositing stETH to immediately sell MOR are just preforming an arbitrage and providing less to the community then they get in MOR rewards.

## Implementation
Can be coded up by the Smart Contract developers that worked on the Capital Smart Contracts.
