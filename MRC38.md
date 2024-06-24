# Title: MRC 38 "The Time Curve for Code"

### Link for Discussion on Discord:
https://discord.com/channels/1151741790408429580/1251994932688719922
### Status: In Discussion

### Authors / Discord Name: Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_) 
### Authors of Proposals On Similar Subjects: mechaverse & kehndry

### Category: MRI #1 Smart Contracts Reference Implementation

## Summary: Fair Stake for MOR
All contributors should have equal access to build MOR by staking their weights. Currently this long-term return is only a natural function of capital rewards.

Fair Stake allows all contributors to be rewarded if they agree not to claim tokens for a set period of time. When instituted, contributors will have the ability to indicate the length of Fair Stake as part of a bid for weights.

Contributors who stake for long periods of time will see a better return on their weights.  See below for a description of economic mechanisms.

## Rationale: Time Equals Aliegnment
Those Contributors of Code should have a way to express their committment to the project. Time is the logical way to express this alignment with the project.

## Dependencies: None.

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

### Mini-FAQ:
- Am I required to stake my weights? No.
- Are my existing weights automatically staked? No.
- Can existing weights be staked? Yes.
- Can any amount of weights be staked? Yes.

**Example:**
>Developer A is bidding on a specific MRC deliverable. They don’t want to undervalue their contribution or be forced to compete with the lowest bidder.  They would rather stand behind good work that they are fairly compensated for.  So, Developer A requests a fair-but-competitive reward in weights, but adds a 48 month Fair Stake of the weights to their bid. Now the MRI maintainer can clearly see a new dimension of value when considering Developer A’s proposal.
>>>

### Value signaling.
Fair Stake allows all contributors to clearly and equally indicate their commitment to growing with Morpheus.  

## Analysis & Models:
- **Emissions Curve Calculator 7.21.2024**
https://docs.google.com/spreadsheets/d/1xTY7keBdPo2Nzm35Wdmu7ngP3NVIDebR/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

- **MOR Power Table**
https://docs.google.com/spreadsheets/d/1uEjozAcnEt-IWaSsu_BbYPRMUCkbwjwv/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

## General Description
It is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming, in return the user will receive an increased MOR reward.

Fair Stake intervals will be posted on GitHub 

## Example MOR Power Multiples
![Example MOR Power Multiples](https://github.com/MorpheusAIs/MRC/assets/1563345/a6de0316-9122-4b52-9c1c-30e60607d612)
**Chart shows examples if the Contributor set time curves starting July 25th 2024**

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

## Using the Multiplier
A multiplier can be applied at deposit, if the user specifies locking period. Or with a separate function on the smart contract - lockClaim(). The lock period is specified in seconds, it can be any interval.
When a multiplier is applied, the user's share of the stETH pool increases, depending on the multiplier.

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:

- the claim lock period can be set by the user or administrator (for non-automatic groups) at any time;
- the claim lock period cannot be decreased; 
- the claim lock period can be increased. At the time of the transaction, the new multiplier will be applied.
- until the end of the lock period, the user will not be able to withdraw their MOR rewards.

## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.
