# MRC 37: Weight Time 
### Status: Implemented

## Summary and Rationale

### Situation
When all weight budgets are depleted, new code will need to be rewarded with weights taken from legacy and orphaned code.

### Challenges 
Weights awarded for an undetermined amount of time may prove to be a disincentive to developers who want clarity on how long their contribution will be valued.  
Healthy open source requires greater reward for contributions who align early without promise of reward.  
MRI maintainers need the ability to value weights as a function of time as well as emission.   

### Solution 
Contributing developers need a knowable amount of snapshots during which weights will be calculated into the block-daily emissions.

> [!NOTE] 
> A contributor is always responsible for the excellent maintenance of their contribution in order to maintain weights.  
> Weight time implies excellent maintenance on behalf of the contributor.   
> New weights are not awarded for maintenance.    

### Implementing this solution 
Moving forward, a contributor will be allowed to include a fixed time for the weights they are requesting. 

For example:  
> “Developer A” proposes donating a feature to Morpheus in exchange for 10,000 weights, fixed for six snapshot periods.  
> MRI Maintainer and Developer A negotiate an acceptable amount of weights for a fixed amount of time to determine the true and present value of the proposed feature. 

### Snapshot evolution
A new column appended the current snapshot table called _number of snapshots Requested_ could be used to express the number of snapshots for which the weights will be considered in emissions.  

<p align="center">New Snapshot table abstract</p>
<b>Snapshot | MRI | Wallet Address | GitHub Handle | Description of Contribution | Proof  | Weights Requested | # of Snapshots Requested</b>
<br><br>
<p align="center">New Snapshot table example</p>
<b>5 | 3 | 0xf93de9fb07f5762a1e3db9a5c687595111928d77 | my GH name | "code does: this" | "http:// Link to proof" | 1250 | 6</b>
<br><br>

> As always, snapshot files can be found in [Contributions](https://github.com/MorpheusAIs/Docs/tree/main/Contributions)

This schedule was also added to [Code Best Practices](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Code%20Providers/Code%20Contributor%20Best%20Practices.md)


### Bidding schedule each month:

![Monthly Dev Bid - Monthly](https://github.com/MorpheusAIs/MRC/assets/76454555/b4c42782-ca45-4a87-9583-12357cab2e85)

To streamline the process of offering and accepting code contributions, the schedule should be implemented.

- By the 7th - Maintainers judge contributions from the previous month
- By the ~8th - Morpheus smart contract updated with new weights
- By the 9th - Contributors submit new bids by filling out the Bid for Weights form (see forms) 
- By the 15th - Maintainers will accept or reject new bidsSub
- By the 31st - Contributors submit a Proof of Contribution (see forms) describing a delivered contribution add the normal information on Github to the [snapshot file](https://github.com/MorpheusAIs/Docs/tree/main/Contributions) for that month.


### Forms
1. Bid for Weights: https://forms.gle/ZBmPXq4jZ3L6qwqR8
2. Proof of Contribution: https://forms.gle/51Bsd4QWoURAXEc7A
   
(These forms are R&D versions, pre MOR.Software)

## Existing weights
None required

## New Weights
None required

## Deliverables
- A Google Doc form that collects Bids for Weights (see above)
- A Google Doc form that collects Proof of Contribution (see above)
- Bidding and Deliverables table (see above)
