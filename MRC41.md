# Title: MRC 41 "The Time Curve For Builders"

### Link for Discussion on Discord: 
https://discord.com/channels/1151741790408429580/1251995756332843189

### Status: In Discussion

## Authors / Discord Name: Anon 866, David Johnston (Smart Agents), Anton (antonb), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_)   

## Category: MRI #1 Smart Contracts Reference Implementation

## Rationale: Time Equals Aliegnment
To implement economic alignment of Builders, it is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming. It is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming, in return the user will receive an increased MOR reward.

## Dependencies: 
None.

## New Weights Requested: 
30,000 Weights

## Existing Weights: 
None.

## Deliverables: Smart Contract Updates 
The Distribution Smart Contract specifically with have a the two functions added.
1. MOR Time Delay function (restrict MOR claims during certain block heights).
2. Power Multiple calculation (update MOR reward calculation).

## Qualification:
Same open source developers that developed the Morpheus Smart Contracts thus far.

## Timelines
4 to 6 weeks from June 21st 2024

## Analysis & Models:
- **Emissions Curve Calculator 7.21.2024**
https://docs.google.com/spreadsheets/d/1xTY7keBdPo2Nzm35Wdmu7ngP3NVIDebR/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

- **MOR Power Table**
https://docs.google.com/spreadsheets/d/1uEjozAcnEt-IWaSsu_BbYPRMUCkbwjwv/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

## Realization
Final MOR reward calculation
When  claim of  the MOR tokens are locked, there will be a multiplier for the user final rewards. Thus the final reward will be calculated by the formula:

final_reward = standard_reward * multiplier

Where the standard_reward: calculated according to the existing rules.

## Calculation of the Multiplier
The multiplier is calculated using the following formula:

multiplier = (end - now)/now + 1;

Where the end: MOR that potentially will be in circulation at the end of lock period for the current group.
Where the now: MOR that is potentially in circulation at the time of transaction execution for the current group.

## Using Tanh Hyperbolic Tangent for this Function in Solidity
- power = (16.61327546) * tanh((x/2625000) / (15.507186 / 2))
- where x is the number of blocks
- 16.61327546 is the max power
- 15.507186 is the number of years left
- 2625000 is number of blocks in a year for Ethereum
- Plug in x for the number of blocks someone is willing to lock up, and this equation will return the power factor
- e.g. let's say someone waits one year = 2625000 blocks 
- 2.1 = 16.61327546 tanh((2625000/2625000) / (15.507186 / 2))
- Power is 2.1 for someone who waits a year
- e.g., 2 years is 4.19
- If there are issues getting tanh to work in solidity, you can create it with this.
- tanh(x) = (e^x - e^(-x)) / (e^x + e^(-x))

## Example Chart
![Example MOR Power Multiples](https://github.com/MorpheusAIs/MRC/assets/1563345/9edcc69a-cdf6-4413-ab30-18d80982c910)
Presumes a July 25th 2024 start date

## Using of Multiplier
A multiplier can be applied at deposit, if the user specifies locking period. Or with a separate function on the smart contract - lockClaim(). The lock period is specified in seconds, it can be any interval.
When a multiplier is applied, the user's share of the stETH pool increases, depending on the multiplier.

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:
- the claim lock period can be set by the user or administrator (for non-automatic groups) at any time;
- the claim lock period cannot be decreased; 
- the claim lock period can be increased. At the time of the transaction, the new multiplier will be applied.
- after the end of the blocking period, the user will continue to receive rewards with the multiplier, until the moment of any transaction on the smart contract (deposit, withdraw, claim), after that the multiplier will not be applied by the user.

## Relation to Builder Rewards
1. Staking of MOR toward a MOR20 Project will inform the reward rate of MOR distributed to that project.
2. Staking MOR will be locked until both: 
A. After the Token Generation Event.
B. After the MOR fees paid to the Morpheus Protocol Owned Liquidity exceed that of the MOR rewards paid out by the Protocol.

## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
6-8 weeks from June 21st 2024.
