# Title: MRC 39 "The Time Curve Staking MOR for Capital Providers"

### Link for Discord: 
https://discord.com/channels/1151741790408429580/1251995170178596966

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
A negative feedback loop is possible in the current mechanism that has been revealed via the real world data. That is to say if the price goes down, the amount of stETH goes down. Because the stETH declines the competition to earn MOR declines. Thus reducing the cost to acquire MOR. So the remaining stETH still gets MOR for 74% less than the ETH it took to earn it. And because there is no time delay function an attacker can play out this game theory and benefit from the declining price and still be making ETH returns regardless of if MOR is $100, $50, $10, $1. Selling all their MOR every week when the Protocol Owned Liquidity buys. Its not about the price being up or down, its a negative feedback loop in being able to withdraw more ETH than contributed instantly. 

Its clear in the data The Time element closes this negative feedback loop. As the price movements up and down over Time make the game of selling all the MOR for ETH too risky for short term holders.

During the bootstrapping period from February 8th 2024 to May 8th 2024, when there was a 90 day delay in the MOR claiming and the tokens were not trading yet, it prevented this negative feedback loop.

**Decision Tree:**
- Is there a real architecture issue to address? Yes or No. **Clearly Yes.**
- If yes, then what is the best mechanism to address the issue. **Time is the only objective function proposed.**
- What should the incentive be to delay MOR claims over time? **The Dilution Rate based Power Factor is the only objective function proposed.**
- How long should the Delay function be set for? **TBD Why Not The Entire Supply Curve?**

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

## Timelines
3 to 4 weeks from June 21st 2024

## Analysis & Models:
- **Emissions Curve Calculator 7.21.2024**
https://docs.google.com/spreadsheets/d/1xTY7keBdPo2Nzm35Wdmu7ngP3NVIDebR/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

- **MOR Power Table**
https://docs.google.com/spreadsheets/d/1uEjozAcnEt-IWaSsu_BbYPRMUCkbwjwv/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

## General Description
It is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming, in return the user will receive an increased MOR reward.
For non-automated groups, the contract administrator may specify such a period.

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

## Applying the Power Factor
A power factor can be applied at deposit, if the user specifies locking period. Or with a separate function on the smart contract - lockClaim(). 
The lock period is specified in seconds, it can be any interval.
When a power factor is applied, the user's "protion" of the stETH pool increases, depending on the power factor.

## Example MOR Power Factor
![ExampleMORPowerFactor](https://github.com/MorpheusAIs/MRC/assets/1563345/b44153b0-021b-4095-b52a-2c121f4bb5ac)
**Chart examples based on July 25th as the date the Contributor executes the MOR claim lock function.**

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:

- MOR Staking period can be set by the user or administrator (for non-automatic groups) at any time;
- MOR Staking period cannot be decreased; 
- MOR Staking period can be increased. At the time of the transaction, the new multiplier will be applied.
- until the end of MOR Staking period, the user will not be able to withdraw their MOR rewards.

## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
4 weeks from June 21st 2024

## Appendix Of Analysis:
A few things to think about as I think about this some since our convo:

(1) To the "Will There Be Enough MOR Available" Qquestion: This only really matters as long as the requisite “costs” that need to be paid in MOR can always be adjusted, it doesn’t really matter if a service/inference/etc need to be paid with 1 or 0.1 MOR if its mainly a factor of price and such prices are adjustable. MOR is highly divisible at 18 decimals so the amount that is in circulation is arbitrary at any given point and price should fix any imbalance there easily enough.
