# Title: MRC 41 "The Time & Dilution MOR Staking For Builders"

### Link for Discussion on Discord: 
https://discord.com/channels/1151741790408429580/1251995756332843189

### Status: 
In Discussion

### Authors / Discord Name: 
Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_), Jeff (Jabo38)    

### Authors of Proposals On Similar Time Related Subjects: 
- mechaverse specifically from MRC 36 https://github.com/MorpheusAIs/MRC/blob/main/MRC36.md
- With extensive feedback and alternative proposals from: kehndry

### Category: 
MRI #1 Smart Contracts Reference Implementation

## Rationale: Time Equals Aliegnment
To implement economic alignment of Builders, it is necessary to implement a functionality where users can specify for what period they want to Stake their MOR tokens. It is necessary to implement a functionality where users can specify for what period they want to Stake the MOR tokens, in return the user will receive an increased reputational signal to their project.

## Dependencies: 
None.

## New Weights Requested: 
30,000 Weights

## Existing Weights: 
None.

## Deliverables: Smart Contract Updates 
The Distribution Smart Contract specifically with have a the two functions added.
1. MOR Staking function (delay MOR claims during certain UTCsecond heights).
2. Power Factor Added To MOR Reward Calculation.

## Qualification:
Same open source developers that developed the Morpheus Smart Contracts thus far.

## Analysis & Models:
- **Emissions Curve Calculator 7.21.2024**
https://docs.google.com/spreadsheets/d/1xTY7keBdPo2Nzm35Wdmu7ngP3NVIDebR/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

- **MOR Power Table**
https://docs.google.com/spreadsheets/d/1uEjozAcnEt-IWaSsu_BbYPRMUCkbwjwv/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

## Realization For Calculating the Power Factors
Final MOR reward calculation
When  claim of the MOR tokens are Staked, there will be a power factor for the user final rewards. Thus the final reward will be calculated by the formula:

final_reward = standard_reward * power factor

Where the standard_reward: calculated according to the existing rules.

### Calculation of the Power Factor
The Power Factor is calculated using the following formula:

Power = (end - now)/now + 1;

Where the end: MOR that potentially will be in circulation at the end MOR Staking period for the current group.
Where the now: MOR that is potentially in circulation at the time of transaction execution for the current group.

## Using Tanh Hyperbolic Tangent for this Function in Solidity (Included in the Smart Contract)
- Below is the function for calculating the Power with a factor cap of ~10.7.
- It works over 16 years: July 25, 2024 12pm UTC to January 26, 2040 12pm UTC
- Power Factor cap reflects a 6 year MOR Staking period.
- A Contributor can Stake for the full 16 years, however they gain no additional Power Factor beyond the first 6 years (10.7 max).

**Function:**
def power_relative(staking_begin_unixtime, staking_end_unixtime):
    power_max=16.61327546
    period_start_unix=1721908800  # July 25, 2024 12:00 UTC
    period_end_unix=2211192000    # January 26, 2040 12:00 UTC

    val = power_max * (np.tanh(2 * ((staking_end_unixtime - period_start_unix) / (period_end_unix - period_start_unix))) - np.tanh(2 * ((staking_begin_unixtime - period_start_unix) / (period_end_unix - period_start_unix))))
    val = min(10.7, val) # keeps value below or equal to 10.7
    val = max(1.0, val) # keeps value above or equal to 1

    return val

## Example Chart
![ExampleMORPowerFactor](https://github.com/MorpheusAIs/MRC/assets/1563345/8ff10a90-cdd3-4d65-9915-59f20fc55dbf)
Presumes a July 25th 2024 start date

## Applying the Power Factor
A power factor can be applied at deposit, if the user specifies MOR Staking period. Or with a separate function on the smart contract - StakingClaim(). 
The MOR Staking period is specified in seconds, it can be any interval.
When a power factor is applied, the user's "protion" of the stETH pool increases, depending on the power factor.

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:

- MOR Staking period can be set by the user or administrator (for non-automatic groups) at any time;
- MOR Staking period cannot be decreased; 
- MOR Staking period can be increased. At the time of the transaction, the new multiplier will be applied.
- until the end of MOR Staking period, the user will not be able to withdraw their MOR rewards.

## Relation to Builder Rewards
1. Staking of MOR toward a MOR20 Project will inform the reward rate of MOR distributed to that project.
2. Staking MOR will be Staked until both: 
A. After the Token Generation Event of a MOR20 Project or Launch o the MRC21 Project.
B. After the MOR fees paid to the Morpheus Protocol Owned Liquidity exceed that of the MOR rewards paid out by the Protocol.

## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
8 weeks from June 21st 2024.
