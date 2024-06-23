# MRC 42

### In Discussion on Discord: https://discord.com/channels/1151741790408429580/1251996042929639434

This proposal sets forth a method for a Contributor to set a Time Delay for their Claims on MOR rewards into the future. In exchange the Contributor receives additional Power in the rewards calcuation. The Power Multiple mirrors closely the Dilution rate (the amount of additional MOR have been Emitted during that period). The intent is to better align the Contributors with the long term benefit of Morpheus as all Contributions regardless of if they are Code, Capital, Compute or Builders require Time to have their positive effect.

**Note for Capital Contributors: Nothing in this proposal changes a Capital Contributors access to their stETH. They can still withdraw their stETH after the normal 7 day period when ever they choose.** However if a Contributor withdraws their stETH they stop getting the Power Multiple applied to their stETH Contributors from the block they made the withdraw.

![Example MOR Power Multiples](https://github.com/MorpheusAIs/MRC/assets/1563345/bef071e3-d607-4020-ba59-b985f8163277)

## The Time Curve General Description MRC
- The unified Time Curve principle. 
- The answer to "Life, the Universe and Everything" is Time.
- How to make contributions to Morpheus **accretive** vs **extractive**.
- The concept is that all Contributions take Time for them to benefit the network, the longer the Time the greater the benefit. 

## Time Seperates All Things
It seperates the Builders from the tourists. The HODLers from the day traders. 
In the Morpheus context, Time seperates the real Contriubtors from short term opportunists.

**To quote Paul Graham:** 
- "If your opponents are opportunists, one way to beat them is to outlast them. 
- Opportunists almost by definition lack staying power."
- https://x.com/paulg/status/1802094669628625272?s=46&t=iOyqtKddsZp1sSUXOguocA

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

![Example MOR Power Multiples](https://github.com/MorpheusAIs/MRC/assets/1563345/94e26b82-d4c7-4b09-b4ce-589caae23481)
**Charts shows example power multiples if the Contributor locked their MOR rewards the 25th of July 2024.**

## MRCs 38, 39, 40, & 41 
These MRCs stand for how to implement Time as a function for each of the four core proofs of Morpheus. 
Code, Capital, Compute and Builders. However the principle is the same across all four and should hold generally.

- **Code MRC 38:** https://github.com/MorpheusAIs/MRC/blob/main/MRC38.md
- **Capital MRC 39:** https://github.com/MorpheusAIs/MRC/blob/main/MRC39.md
- **Compute MRC 40:** https://github.com/MorpheusAIs/MRC/blob/main/MRC40.md
- **Builders MRC 41:** https://github.com/MorpheusAIs/MRC/blob/main/MRC41.md
