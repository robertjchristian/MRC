# MOR Weights MRC Proposal
March 14, 2024

NOTE:  Consider the updated [Weights Guide](https://github.com/MorpheusAIs/Docs/blob/6a094f60e3081ac9ec2ec8d1ee4ecebfbbee1375/Guides/Code%20Contributor%20Weights%20Guide.md#march-8th-to-april-8th-2024-implied-value-of-a-weight-calculation-snapshot-3--126-usd-per-weight) for a complete understanding of weight value during the bootstrapping period. 
---

## Status
April 1, 2024: IMPLEMENTED

---

## Objective
This aims to increase the versatility of MOR weights.

## Summary
Per the White Paper, the Yellowstone Paper, and the Morpheus Email, The MOR weights are a means to describe the allocation of MOR emissions.
The MOR smart contracts measure MOR emissions as type:integer, disallowing a fraction of a weight to exist. 
The number of MOR weights for code are halving every twelve months.

50% of all weights will be distributed the 1st year.
Weights must be maintained by the weight’s associated contributor.
  
## Pending Problem

As the number of new weights available decreases, the value of each weight increases.  Without the ability to be awarded a fraction of a weight, It will soon be the case that the smallest awardable amount for code contributions will equate to multiple thousands of dollars.
In this scenario, the project will be forced to over-reward for simple contributions, disincentivizing maintenance and innovations.

Using conservative estimates, information collected by the community reflects:
The remaining 1,548 weights have an implied value of $992,268 USD. Spread over the remaining 5 months (presuming no more increases in the weight value in the next 5 snapshots), that equals $198,453 USD of weight rewards available each month.

## Solution - MORbase the weights by 2,000.
If the maintainers agree, the weights published in March 2024 should be MORbased by 2,000 when April 2024 weights are calculated and sent to chain.  Similarly, the remaining weight pool should also be MORbased by 2,000 so that the value of current weights don’t dilute. 

### Table I - to the contributor:
Contributor A has 38 weights in the March 2024 weights update.
March weights = 38
April weights = 76,000

### Table II - to the project:
The total weights available are also rebased. 
March Total Weights = 50,000
April Total Weights = 100,000,000

[38 / 500] = [76,000 / 100,000,000]
Existing weights holders maintain their proportion of their existing weights.

### The result to the project will be:
Increased granularity in the allocation of weights;
Fair-market buying power;
The ability to include more developers in future development.

In the future, and if market conditions require it, this tactic could be repeated. 

## Conclusion
MORbasing the weights by 2,000 gives Morpheus future flexibility. 
