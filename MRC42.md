# Title: MRC 42 "Time & Dilution Based MOR Staking Available To All Contributor Types"

### Authors / Discord Name: 
Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_), Jeff (Jabo38)  

### Authors of Proposals On Similar Time Related Subjects: 
- mechaverse specifically from MRC 36 https://github.com/MorpheusAIs/MRC/blob/main/MRC36.md
- With extensive feedback and alternative proposals from: kehndry

### In Discussion on Discord: 
https://discord.com/channels/1151741790408429580/1251996042929639434

## Introduction - Rational / General Description
This proposal sets forth a method by which Contributors can Stake MOR reward claims to a time in the future.
In exchange for Staking MOR for a period of time, the Contributor gets a "Power Factor" appliced to the calculation of their MOR rewards each UTC second. 
This Power Factor mirrors the the Delution rate the Contributor experiences while Staking the MOR. 

It is worth emphasizing that, none of these MOR Staking proposals increase the amount of MOR token emissions that are created. Rather, it changes a Contributors proportional rights to the amount of tokens that are being emitted during a period they contribute their value. In a similar way that increasing a miner's hash rate increases the amount of the portion of Bitcoin they mine.

**For Capital Providers Please Note:** 
- Nothing in this proposal changes the ability of a Contributor to withdraw their stETH (beyond the normal 7 days), only the claiming of MOR rewards is delayed. However when a Contributor withdraws their stETH their reward factor no longer applies after the UTC second time of their withdraw.

![ExampleMORPowerFactor](https://github.com/MorpheusAIs/MRC/assets/1563345/be4492a8-e050-4deb-8270-2029e39386d9)
**Charts shows example power factor if the Contributor Staked their MOR token claims the 25th of July 2024.**

## The Time Curve General Principles for MRCs 38, 39, 40, & 41.
- The Power Factor principle mirroring Dilution rates can be used across Contributor types. 
- The answer to "Life, the Universe and Everything" is Time.
- How to make contributions to Morpheus **accretive** vs **extractive**.
- The concept is that All Contributions (Code, Capital, Compute or Builders) take Time for them to benefit the network, the longer the Time the greater the benefit. 
- Time seperates the Builders from the tourists. The HODLers from the day traders. 
- In the Morpheus context, Time seperates the real Contriubtors from short term opportunists.

## The Time Power Factor (Shortened "Power")
Rather than pick a "magic" number for the "Power Factor" function, this number can best be set by looking at the actually Dilution Rate the person exeperiences from Staking their MOR tokens for a specific period of time.

**For example:**
- On July 25th 2024 2,384,564 MOR will have been emitted.
- On July 25th 2025 7,338,234 MOR will have been emitted.
- Thus 4,953,670 MOR have been emitted since the Time delay for claims began.
- In the case the user choses to Stake their MOR claims for this 12 month period, they experience 207% dilution.  
- So the Time Power Factor should be around the same 2X. 

- In other words the Base reward as calculated by the number of stETH staked in the case of capital or the weights held in the case of a Code Contributor is mulipled by the Power Factor. 
- The result of this multiplication is then divided by the total stETH * Power or Weights * Power of ALL Contributors in that group to determine the individual Contributors proportionality of the MOR rewards that UTC second.

**For Example:**
- 1 stETH with a 207% Power Factor would have a result of 2.07
- This 2.07 sum would be divided by the total stETH staked (or yield provided in a future yield agnostic version) post Power Factor.
- If 100 stETH were already staked the porportion of rewards for the 1 stETH staker after his deposit would be equal to 2.07 out of 102.07 
- Which equals 2.02% of the of the MOR emissions during that UTC second.

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
