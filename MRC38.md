# MRC 38

# The Time Curve for Code

## Link for Discussion on Discord:
https://discord.com/channels/1151741790408429580/1251994932688719922

## Analysis & Models:
- **Emissions Curve Calculator 7.21.2024**
https://docs.google.com/spreadsheets/d/1xTY7keBdPo2Nzm35Wdmu7ngP3NVIDebR/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

- **MOR Power Table**
https://docs.google.com/spreadsheets/d/1uEjozAcnEt-IWaSsu_BbYPRMUCkbwjwv/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

## General Description
It is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming, in return the user will receive an increased MOR reward.

For non-automated groups like this Code one, the contract administrator may manually enter such a period to match the one expressed on Github.

## Example MOR Power Multiples
![ExampleMORPowerMultiples](https://github.com/MorpheusAIs/MRC/assets/1563345/0ce2bda9-20bf-4cbb-8ba6-1538952b578b)
**Chart shows examples if the Contributor set time curves starting July 25th 2024**

## Realization
Final MOR reward calculation
When  claim of  the MOR tokens are locked, there will be a multiplier for the user final rewards. Thus the final reward will be calculated by the formula:

final_reward = standard_reward * multiplier

Where the standard_reward: calculated according to the existing rules.

Calculation of the multiplier
The multiplier is calculated using the following formula:

multiplier = (end - now)/now + 1;

Where the end: MOR that potentially will be in circulation at the end of lock period for the current group.
Where the now: MOR that is potentially in circulation at the time of transaction execution for the current group.

## Using the Multiplier
A multiplier can be applied at deposit, if the user specifies locking period. Or with a separate function on the smart contract - lockClaim(). The lock period is specified in seconds, it can be any interval.
When a multiplier is applied, the user's share of the stETH pool increases, depending on the multiplier.

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:

- the claim lock period can be set by the user or administrator (for non-automatic groups) at any time;
- the claim lock period cannot be decreased; 
- the claim lock period can be increased. At the time of the transaction, the new multiplier will be applied.
- until the end of the lock period, the user will not be able to withdraw their MOR rewards.

## Changes to smart contracts**
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
2-3 weeks from June 21st 2024
