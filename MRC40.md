# Title: MRC 40 "The Time Curve For Compute"

### Link for Discussion on Discord: 
https://discord.com/channels/1151741790408429580/1251995364693774336

### Status: In Discussion

## Authors / Discord Name: Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel) Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_)   

## Category: MRI #1 Smart Contracts Reference Implementation

## Rationale: Time Equals Aliegnment
To implement economic alignment of Compute Providers, it is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming, in return the user will receive an increased MOR reward and more reputation.

- 1. Staked MOR can inform the likelihood of the Compute provider being selected. Weight in Compute Provider Repution.
- 2. Stake MOR can inform the maximum reward a Compute Provider can earn. So for example if 100 MOR are Staked for 1 Year, then the most the Compute Provider can earn is 100 MOR during 1 year of providing Compute.

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
3 to 4 weeks from June 21st 2024

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

## Realization For Calculating the Multiples
Final MOR reward calculation
When  claim of  the MOR tokens are locked, there will be a multiplier for the user final rewards. Thus the final reward will be calculated by the formula:

final_reward = standard_reward * multiplier

Where the standard_reward: calculated according to the existing rules.

Calculation of the multiplier
The multiplier is calculated using the following formula:

multiplier = (end - now)/now + 1;

Where the end: MOR that potentially will be in circulation at the end of lock period for the current group.
Where the now: MOR that is potentially in circulation at the time of transaction execution for the current group.

## Using Tanh Hyperbolic Tangent for this Function in Solidity (Included in the Smart Contract)
- Below is the function for calculating the Power with a multiple cap of ~7.46.
- It works over 16 years: July 25, 2024 12pm UTC to January 26, 2040 12pm UTC
- Power Multiple cap reflects a 4 year delay on Claim locks.
- A Contributor can lock for the full 16 years, however they gain no additional Multiple beyond the first 4 years (7.46 max). 

**Function:**
def power_relative(x_init, x_final, power_max=16.61327546, b_start=20387806, b_end=61140686):
    return min(7.464310556, power_max * (np.tanh(2 * ((x_final - b_start) / (b_end - b_start))) - np.tanh(2 * ((x_init - b_start) / (b_end - b_start)))))

**Terms:**
x_init: the ethereum block height when the user chooses to begin staking
x_final: the ethereum block height when the user's lockup period ends
b_start: estimated block height on July 25, 2024 12pm UTC
b_end: estimated block height on January 26, 2040 12pm UTC

## Using of multiplier
A multiplier can be applied at deposit, if the user specifies locking period. Or with a separate function on the smart contract - lockClaim(). The lock period is specified in seconds, it can be any interval.
When a multiplier is applied, the user's share of the stETH pool increases, depending on the multiplier.

## Example Multiples in Chart
![Example MOR Power Multiples](https://github.com/MorpheusAIs/MRC/assets/1563345/0e7f91be-d223-49e0-972f-a55500d6464d)
**Presumes a July 25th 2024 Start Date**

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:
- the claim lock period can be set by the user or administrator (for non-automatic groups) at any time;
- the claim lock period cannot be decreased; 
- the claim lock period can be increased. At the time of the transaction, the new multiplier will be applied.
## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
4 to 6 weeks from June 21st 2024.
