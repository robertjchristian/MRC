# Title: MRC 39 "The Time Curve Staking MOR for Capital"

### Link for Discord: 
https://discord.com/channels/1151741790408429580/1251995170178596966

### Status: 
In Discussion

### Authors / Discord Name: 
Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_)   

### Category: 
MRI #1 Smart Contracts Reference Implementation

## Rationale: Time Equals Aliegnment
A negative feedback loop is possible in the current mechanism that has been revealed via the real world data. That is to say if the price goes down, the amount of stETH goes down. Because the stETH declines the competition to earn MOR declines. Thus reducing the cost to acquire MOR. So the remaining stETH still gets MOR for 74% less than the ETH it took to earn it. And because there is no time delay function an attacker can play out this game theory and benefit from the declining price and still be making ETH returns regardless of if MOR is $100, $50, $10, $1. Selling all their MOR every week when the Protocol Owned Liquidity buys. Its not about the price being up or down, its a negative feedback loop in being able to withdraw more ETH than contributed instantly. 

Its clear in the data The Time element closes this negative feedback loop. As the price movements up and down over Time make the game of selling all the MOR for ETH too risky for short term holders.

During the bootstrapping period from February 8th 2024 to May 8th 2024, when there was a 90 day delay in the MOR claiming and the tokens were not trading yet, it prevented this negative feedback loop.

**Decision Tree:**
- Is there a real architecture issue to address? Yes or No. **Clearly Yes.**
- If yes, then what is the best mechanism to address the issue. **Time is the only objective function proposed.**
- What should the incentive be to delay MOR claims over time? **The Dilution Rate based Power Multiple is the only objective function proposed.**
- How long should the Delay function be set for? **TBD Why Not The Entire Supply Curve?**

## Dependencies: None.

## New Weights Requested: 30,000 Weights

## Existing Weights: None.

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

## General Description
It is necessary to implement a functionality where users can specify for what period they want to lock the MOR token claiming, in return the user will receive an increased MOR reward.
For non-automated groups, the contract administrator may specify such a period.

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
     return max(1.0, min(7.464310556, power_max * (np.tanh(2 * ((x_final - b_start) / (b_end - b_start))) - np.tanh(2 * ((x_init - b_start) / (b_end - b_start))))))

**Terms:**
- x_init: the ethereum block height when the user chooses to begin staking
- x_final: the ethereum block height when the user's lockup period ends
- b_start: estimated block height on July 25, 2024 12pm UTC
- b_end: estimated block height on January 26, 2040 12pm UTC

## Using of multiplier
A multiplier can be applied at deposit, if the user specifies locking period. Or with a separate function on the smart contract - lockClaim(). The lock period is specified in seconds, it can be any interval.
When a multiplier is applied, the user's share of the stETH pool increases, depending on the multiplier.

## Example MOR Power Multiple
![ExampleMORPowerMultiples4Years](https://github.com/MorpheusAIs/MRC/assets/1563345/96373dcd-187c-49e4-b2af-e3954616adc0)
**Chart examples based on July 25th as the date the Contributor executes the MOR claim lock function.**

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:
- the claim lock period can be set by the user or administrator (for non-automatic groups) at any time;
- the claim lock period cannot be decreased; 
- the claim lock period can be increased. At the time of the transaction, the new multiplier will be applied.
- until the end of the lock period, the user will not be able to withdraw their rewards, but will be able to withdraw stETH.

after the end of the blocking period, the user will continue to receive rewards with the multiplier, until the moment of any transaction on the smart contract (deposit, withdraw, claim), after that the multiplier will not be applied by the user.

## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
4 weeks from June 21st 2024
