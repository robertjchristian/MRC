# Title: MRC 42 "Time Curve Based MOR Staking Available To All Contributor Types"

### Authors / Discord Name: 
Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_) 

### In Discussion on Discord: 
https://discord.com/channels/1151741790408429580/1251996042929639434

## Introduction
This proposal sets forth a method by which Contributors can Delay the Claims of their MOR rewards to a time in the future.
In exchange for Delaying their claims of MOR for a period of time, the Contributor gets a "Power Multiple" appliced to the calculation of their MOR rewards each block. This Power Multiple mirrors the the Delution rate the Contributor experiences while delaying the Claim. 

**For Capital Providers Please Note:** 
- Nothing in this proposal changes the ability of a Contributor to withdraw their stETH (beyond the normal 7 days), only the claiming of MOR rewards is delayed. However when a Contributor withdraws their stETH their reward Multiple no longer applies after the block time of their withdraw.

![ExampleMORPowerMultiples4Years](https://github.com/MorpheusAIs/MRC/assets/1563345/353978c2-5a81-4ac3-8271-f4f60d602f21)
**Charts shows example power multiples if the Contributor locked their MOR rewards the 25th of July 2024.**

## The Time Curve General Description MRC
- The unified Time Curve principle. 
- The answer to "Life, the Universe and Everything" is Time.
- How to make contributions to Morpheus **accretive** vs **extractive**.
- The concept is that All Contributions (Code, Capital, Compute or Builders) take Time for them to benefit the network, the longer the Time the greater the benefit. 
- Time seperates the Builders from the tourists. The HODLers from the day traders. 
- In the Morpheus context, Time seperates the real Contriubtors from short term opportunists.

## The Time Power Multiple (Shortened "Power")
Rather than pick a "magic" number for the "Time Power Multiple" function, this number can best be set by looking at the actually Dilution Rate the person exeperiences from locking their MOR tokens for a specific period of time.

**For example:**
- On July 25th 2024 2,384,564 MOR will have been emitted.
- On July 25th 2025 7,338,234 MOR will have been emitted.
- Thus 4,953,670 MOR have been emitted since the Time delay for claims began.
- In the case the user choses to lock their MOR claims for this 12 month period, they experience 207% dilution.  
- So the Time Power Multiple should be around the same. 

- In other words the Base reward as calculated by the number of stETH staked in the case of capital or the weights held in the case of a Code Contributor is mulipled by the Time Power Multiple. 
- The result of this multiplication is then divided by the total stETH * Power or Weights * Power of ALL Contributors in that group to determine the individual Contributors proportionality of the MOR rewards that block.

**For Example:**
- 1 stETH with a 207% Power multiple would have a result of 2.07
- This 2.07 sum would be divided by the total stETH staked (or yield provided in a future yield agnostic version) post Power multiple.
- If 100 stETH were already staked the porportion of rewards for the 1 stETH staker after his deposit would be equal to 2.07 out of 102.07 
- Which equals 2.02% of the of the MOR emissions during that block.

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

## MRCs 38, 39, 40, & 41 
These MRCs stand for how to implement Time as a function for each of the four core proofs of Morpheus. 
Code, Capital, Compute and Builders. However the principle is the same across all four and should hold generally.

- **Code MRC 38:** https://github.com/MorpheusAIs/MRC/blob/main/MRC38.md
- **Capital MRC 39:** https://github.com/MorpheusAIs/MRC/blob/main/MRC39.md
- **Compute MRC 40:** https://github.com/MorpheusAIs/MRC/blob/main/MRC40.md
- **Builders MRC 41:** https://github.com/MorpheusAIs/MRC/blob/main/MRC41.md

## Conclusion: To quote Paul Graham:
- "If your opponents are opportunists, one way to beat them is to outlast them. 
- Opportunists almost by definition lack staying power."
- https://x.com/paulg/status/1802094669628625272?s=46&t=iOyqtKddsZp1sSUXOguocA
