# MRC 37: Fixed Weight Time Minimum 
#### Status: In Discussion
### Summary and Rationale
##### Situation
When all weight budgets are depleted, new code will need to be rewarded with weights taken from legacy and orphaned code.
##### Challenges 
Weights awarded for an undetermined amount of time may prove to be a disincentive to developers who want clarity on how long their contribution will be valued.
Healthy open source requires greater reward for contributions who align early without promise of reward.
MRI maintainers need the ability to value weights as a function of time as well as emission. 
##### Solution 
Contributing developers need a Fixed Minimum Time during which weights will be calculated into the block-daily emissions.

NOTE:  A contributor is always responsible for the excellent maintenance of their contribution in order to maintain weights.  Minimum time implies excellent maintenance on behalf of the contributor.  New weights are not awarded for maintenance.    
Implementing this solution 

Moving forward, a contributor will be allowed to include a fixed time for the weights they are requesting. For example:

> “Developer A” proposes donating a feature to Morpheus in exchange for 10,000 weights, fixed for six snapshot periods.
> MRI Maintainer and Developer A negotiate an acceptable amount of weights for a fixed amount of time to determine the true and present value of the proposed feature. 

##### Bidding schedule each month:
To streamline the process of offering and accepting code contributions, the schedule should be implemented.

- By the 7th - Maintainers judge contributions from the previous month
- By the ~8th - Morpheus smart contract updated with new weights
- By the 9th - Contributors submit new bids by filling out the Bid for Weights form (see forms) 
- By the 15th - Maintainers will accept or reject new bidsSub
- By the 31st - Contributors submit a Proof of Contribution (see forms) describing a delivered contribution add the normal information on Github to the snapshot file for that month.

This schedule was also added to Code Best Practices on Github.https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Code%20Providers/Code%20Contributor%20Best%20Practices.md

###### Forms
1. Bid for Weights:  https://forms.gle/51Bsd4QWoURAXEc7A
2. Proof of contribution  https://forms.gle/51Bsd4QWoURAXEc7A
   
(These forms are R&D versions, pre MOR.Software)

#### Natural alignment with the phases of Bootstrapping. 

This solution presently recognizes four phases of weight assessment.  Weights are protected differently based on these classifications.

##### Phase 1 - Zero reward mechanism.  
This is loosely defined by the areas that were important enough at the time to become MRIs. This was the  period of greatest risk to the contributor.

##### Phase 2 - Post signaling, pre-liquidity.  
This roughly overlaps with the Bootstrapping period between Feb 8, and May 8, 2024. Covers weights that rewarded contributions needed to build community momentum

##### Phase 3 - Fixed Market Reward
Marked as starting when tokens could be swapped on Uniswap, and risk of reward was eliminated.

##### Phase 4 - Recycled Rewards
After all weights have been initially rewarded and begin to be recycled for new contributions. This assumes that the Community Bucket contract (based on the white paper)  is able to reward continued efforts aligned with Phase 2.

##### Protection Boundaries
Weights allocated in Phase 1 that required blind faith in the project cannot be recycled. Weights allocated in Phase 2 that cannot be rewarded via the community bucket when available, can be recycled after a fixed numner of months, TBD. Weights allocated in Phases 3 and 4 will have Fixed Weight Time Minimums negotiated solely between MRI maintainers and Contributors.

#### Value
Developers can forecast the number of weights associated with a contribution across the MOR20 universe of projects.
#### Existing weights
None required
#### New Weights
None required
#### Deliverables
- A Google Doc form that collects Bids for Weights (see above)
- A Google Doc form that collects Proof of Contribution (see above)
- Bidding and Deliverables table (see above)
