# MRC 30 - The Evolution of Code Weights

**Author(s)**: Nebuchadnezzar Crew

**Categories:**
1) Code Proofs & Dashboards - This MRC proposes the foundational manner in which code contributions are rewarded. 
2) Capital Proofs Extending - As the Whitepaper is the core ‘Capital Proofs Extending’ MRC, it serves as the basis for the origination of the 24% of emissions going to Code Contributors and ultimately the weights concept.

# Summary

The general approach of this paper is to ensure all involved as Code Contributors feel assured about the distribution of weights historically, currently, and going forward. It seeks to define aspects of the process to ensure consistency across the life of Morpheus such that Contributors have full insight into the process of allocating weights allowing them to make educated decisions regarding their efforts. 
The goal is to establish a structure that encourages participation by clarifying the process, setting clear expectations, rewarding past contributions, and explaining how to maintain weights. This also aims to prevent the arbitrary removal of weights by implementing a clear framework of how weights are removed, fostering a more transparent and equitable environment.
The paper walks through several recommendations on how to adjust the current state of the monthly snapshots and weight allocations. The goal of these suggestions is to:

1) Incentivize participants to contribute long term
2) Simplify as much of the process as possible and design allocations in such a way to avoid foreseeable future complications. 
3) Define key aspects to provide increased clarity and transparency to the community to reduce future questions and confusion.
4) Maximize the value of weights and their impact on Morpheus.

The paper outlines the basics around the suggested updates for the following topics:

1) Combine available weights remaining for Year 1 and Year 2
2) Establish the schedule for monthly distribution of weights
3) Allocate monthly weights by MRI
4) Implement a Tier System for Contributions
5) Define process for removal of historical weights

# Rationale & Value Proposition 

The primary topics of this MRC will each walk through the current status, the proposed update, and any additional notes that help to define the rationale for the suggested updates and the overall value proposition. 

## Combine Available Weights Remaining for Year 1 & Year 2

**Current Status:**
To stay under the 50,000,000 cap for Year 1, there are only 1,609,580 weights left, equivalent to 321,916 weights per month.
After Year 1, the cap increases to 75,000,000 for Year 2, and thus there are 25,000,000 weights for Year 2, equivalent to 2,083,333 weights per month.
The result is that Contributors for the next 5 months might be under-rewarded relative to the 12 months following.

**Proposed Update:**
By combining the weights available over the next 17 months, this smooths out the disparity between the remaining 5 months of Year 1 and the 12 months of Year 2.
This would combine the 26,609,580 weights to be distributed across the next 17 months, equivalent to an equal spread of 1,565,269 weights per month.

**Additional Notes:** The tables below provide an example of how the current state and the proposed update might look, highlighting the disparity that would arise in the current structure. 

**Current Emission Schedule**
|# |Month	| Year | Weights Distributed |	Cumulative Weights |
| --------- | --------- | --------- | --------- | --------- |
| 1-6	| March	| 2024	| 46,924,000	| 46,924,000|
| 7	| April	| 2024	| 1,466,420	| 48,390,420|
| 8	| May	| 2024	| 321,916	| 48,712,336|
| 9	| June	| 2024	| 321,916	| 49,034,252|
| 10	| July	| 2024	| 321,916	| 49,356,168|
| 11	| August	| 2024	| 321,916	| 49,678,084|
| 12	| September	| 2024	| 321,916	| 50,000,000|
| 13	| October	| 2024	| 2,083,333	| 52,083,333|
| 14	| November	| 2024	| 2,083,333	| 54,166,667|
| 15	| December	| 2024	| 2,083,333	| 56,250,000|
| 16	| January	| 2025	| 2,083,333	| 58,333,333|
| 17	| February	| 2025	| 2,083,333	| 60,416,667|
| 18	| March	| 2025	| 2,083,333	| 62,500,000|
| 19	| April	| 2025	| 2,083,333	| 64,583,333| 
| 20	| May	| 2025	| 2,083,333	| 66,666,667|
| 21	| June	| 2025	| 2,083,333	| 68,750,000|
| 22	| July	| 2025	| 2,083,333	| 70,833,333|
| 23	| August	| 2025	| 2,083,333	| 72,916,667|
| 24	| September	| 2025	| 2,083,333	| 75,000,000| 

**Sample Proposed Schedule**
|# |Month	| Year | Weights Distributed |	Cumulative Weights |
| --------- | --------- | --------- | --------- | --------- |
| 1-6	| March	| 2024	| 46,924,000	| 46,924,000|
| 7	| April	| 2024	| 1,466,420	| 48,390,420|
| 8	| May	| 2024	| 1,565,269	| 49,955,689|
| 9	| June	| 2024	| 1,565,269	| 51,520,959|
| 10	| July	| 2024	| 1,565,269	| 53,086,228|
| 11	| August	| 2024	| 1,565,269	| 54,651,498|
| 12	| September	| 2024	| 1,565,269	| 56,216,767|
| 13	| October	| 2024	| 1,565,269	| 57,782,036|
| 14	| November	| 2024	| 1,565,269	| 59,347,306|
| 15	| December	| 2024	| 1,565,269	| 60,912,575|
| 16	| January	| 2025	| 1,565,269	| 62,477,845|
| 17	| February	| 2025	| 1,565,269	| 	64,043,114|
| 18	| March	| 2025	| 1,565,269	| 65,608,384|
| 19	| April	| 2025	| 1,565,269	| 67,173,653| 
| 20	| May	| 2025	| 1,565,269	| 68,738,922|
| 21	| June	| 2025	| 1,565,269	| 70,304,192|
| 22	| July	| 2025	| 1,565,269	| 71,869,461|
| 23	| August	| 2025	| 1,565,269	| 73,434,731|
| 24	| September	| 2025	| 1,565,269	| 75,000,000| 

## Establish the Schedule for Monthly Distribution of Weights

**Current Status:**
Weights are currently given out based on a USD value. This is made complicated by establishing and tracking a fair value of $MOR as well as putting weights at the mercy of fluctuations in price. GitHub maintainers approve weights as they come in, meaning that in a given month, there could be a large amount of weights disbursed, or there could be very few - based on both the submissions and the prevailing price of $MOR. 
This approach can result in situations like we have in Year 1 - where in order to stay within the annual cap limits, the weights wound up being frontloaded and now for the remaining 5 months of the year, there is an extremely limited number of weights. This could reduce the incentive for developers to contribute, or they may at a minimum delay their contributions until more weights are available.
This approach also could be very detrimental if $MOR price were to experience a significant drop - Using the April 8th snapshot as an example, if the price would have been $10 instead of $100, this would have required ~15M weights to be distributed since they are tied to a USD value. This would instantly destroy the ability to stay within the proposed caps for the year and potentially for the whole project.

**Proposed Update:**
The weights available for each month are pre-defined. All those weights will be distributed on a pro-rata basis to Contributors from that month. For example, if 1,565,269 weights are available for the May 8th snapshot and a Contributor was responsible for 10% of the impact, then exactly 1,565,269 weights will be distributed for the month, with 156,527 weights to that Contributor.
As weights are relevant for up to 16 years, this also ensures a smoother balance versus in the current situation where if price is extremely high (or low), then Contributors in that month would receive an extremely small (or large) amount of weights to achieve the appropriate USD valuation. 
Defining rewards by MOR instead of USD also encourages long term alignment for the Contributors with the project. Lastly, this update would remove much of the effort and complexity related to the process that would exist if USD denominations are continued. 

**Additional Notes:**
Sticking with a USD basis approach greatly increases the effort and complexity going forward. It would require the following steps that are not currently in place nor defined: 
1) Determining which day/period, price [opening, closing, average], is used for implied value
2) Determining which market(s) are used for price feeds
3) Determining how to deal with extreme prices which would deplete annual weight budget (i.e. example where if $MOR is $10, then the entire annual budget of weights would be spent in 1 month)
4) Determining how to deal with extreme prices which would suppress total weights (i.e. example where if $MOR is $1,000 for a sustained period of time, then there may only be 1,000,000 weights distributed in Year 2 which strays from the halving schedule provided to the community).
5) Defining if MOR emissions to code are defined as the fiscal period, the upcoming 12 months, or some other metric for calculation purposes
6) Determining how to handle deprecated weights, since they’d be removed from the denominator when distributing pro-rata emissions 
7) Determining how to estimate future overages/underages on monthly weight allocations and their impact on current month valuation. 
8) It could also result in stretches of months where Contributions are discouraged, either due to high $MOR price and therefore low available weights as well as if the start of a year disburses a majority of the weights [like in the current year] and then the final months of that year are extremely sparse in the weights they can offer.  

## Allocate Monthly Weights by MRI ##

**Current Status:**
Weights are submitted into one aggregated pool, where MRI owners and GitHub maintainers review and approve or reject the submissions. This results in a labor intensive process of comparing apples to oranges, i.e. it is difficult to compare the value of something like expanding Morpheus to a new chain versus developing a smart contract to support $MOR staking. These situations involve not only different subject matters, but also different MRI owners who will each have their own subjectivity at play.

**Proposed Update:**
Each MRI is allocated a specific number of weights to be distributed. This aids in aligning efforts by category such that they become easier to compare which contributions have a larger impact compared to another. This also consolidates the decision for those allocations into an individual MRI owner who is better suited to evaluate consistently across contributions instead of the subjectivity that is added when different MRI owners are evaluating different contributions and trying to compare.

**Additional Notes:** 
The particular allocation to each MRI could be in any manner that the MRI owners see fit. It could be an even spread across each of them, or it could allocate more to MRIs considered more impactful. It can also adjust over time - perhaps for the first several months while still in the early stages, it remains one big bucket, and then when Phase 2 goes live, additional allocations could be given to help bring Compute online, and when Phase 3 goes live, additional allocations could be given to help jumpstart the Community efforts. 

Sample Outline of Monthly Weights by MRI (numbers are hypothetical)
| MRI          | May 2024 | June 2024 |
| ----------------------- | ---------- | ----------------------------- | 
| Smart Contracts     |    1,000   |    2,000          |
| Smart Agent Tools & Examples |    1,000   |  1,000    |
| Morpheus Local Desktop / Mobile |      500   |  2000     |
| TCM / MOR20 |    3,500   |   1,000  |
| Protection Fund            |   1,000   |  1,000 |
| Capital Proofs Extending |   4,000   | 1,000  |
| Compute Proofs MOR / Lumerin     |   1,000   |  2,000  |
| Code Proofs & Dashboards      |   1,000   |      2,000    |
| Frontend Proofs & Examples      |   1,000   |      2,000    |
| Interoperability               |   1,000   |      1,000    |
| Total                |   15,000   |      15,000    |

## Implement a Tier System for Contribution
**Curent Status:**
Contributors analyze what they thought the USD value was of their impact and submit the corresponding weights. 

**Proposed Updates:**
Moving forward, the weights will be given out on a pro-rata basis compared against the impact of all other contributions for the month. To help standardize this process, this MRC proposes a three tier system. When submitting their requests to the snapshot, the contributor will provide:
1) Wallet Address
2) Link to Work
3) (New) MRI Bucket
4) (New) Tier of Contribution
5) Description of Contribution

Tiers will be defined in detail throughout the development of the deliverables.

## Define Process for Removal of Historical Weights
**Current Status:**
At each snapshot, the GitHub maintainers review the prior contributions and determine if any weights are no longer relevant, have been superseded, or are improperly maintained. 
The issue that arises is if the owner of those weights is simply unaware that they’ve failed their duties required to maintain the weights. They could be a good actor and fully capable of making necessary updates, but were unaware that updates are needed.

**Proposed Update:**
Given how valuable weights are, Contributors should be given a warning prior to their weights being removed. This process could consist of: 
1) Warning from GitHub maintainers or MRI owners identifying the weights considered at-risk and the reasoning
2) Contributor is given a one month/snapshot period to bring the code/materials into good standing
3) GitHub maintainers evaluate during the next snapshot if the effort is satisfactory
4) If satisfactory, then weights stay with original Contributor
5) If unsatisfactory, then weights are removed from original Contributor and any community member can takeover the duties to earn new weights

## Dependencies 
Code Contributor Weights Guide - 
https://github.com/MorpheusAIs/Docs/blob/main/Guides/Code%20Contributor%20Weights%20Guide.md - This is not a dependency in the sense that the existing Weights Guide needs to be completed before this MRC can be effective, but it is a dependency in the sense that the Weights Guide has governed the process up to this point. Careful consideration needs to be paid to maintain the foundation created by that document, and that no contradictions or complications arise.

## New Weights Requested 
This MRC proposes a revamp to the weights system where a number of weights are not requested. As part of our deliverable, we will provide a framework for how this new approach will be completed.

## Existing Weights
As this MRC touches on a variety of topics, it focuses on several different buckets of existing weights. None of these buckets are getting replaced, rather this is an enhancement to add new functionality to the existing design. These existing weights exist across a number of MRIs as noted in the “Category” section above.

## Deliverables 
1) Updated Code Contributors Weights Guide - The updated guide will maintain the historical process used so that there is a trail for posterity sake, and that if anyone (perhaps years from now) wants to understand the first 7 months of weight allocations, it will be documented. The updated guide will then expand to define the new processes, complete with calculations, tables, definitions, and appropriate appendices. 
2) $MOR Code Contributors Emission Schedules - The calculations and tables for the emissions schedule to code contributors
3) Allocation by MRI Template - The template for MRI owners to use when determining the allocation of monthly weights between the various MRIs.
4) Contribution Impact Framework - As the proposal goes away from developers requesting a specific number of weights, and moves towards the pro-rata impact, it is important to have a standardized methodology so contributions are compared on a level playing field.
5) Weight Maintenance Guide - This will outline the steps undertaken whenever a particular batch of weights are called into question for lack of management. We’ll outline the steps that will be taken and create a standardized template to walk through the process.
6) Updated Snapshot Template - Since users will not be submitting requests for a defined number of weights, the authors will provide an updated version of the Snapshot document to
7) Pro-Rata Calculator - This can be used by MRI owners to do the actual calculation, but also will be open source so that Contributors can plug in their own estimates to get ideas as to how many weights their contributions will translate to 

## Background / Experience of Author / Implementer 
The Nebuchadnezzar Crew has been heavily involved in Morpheus. They have authored or collaborated on close to 10 MRCs and have been instrumental in much of the design and framework of critical aspects of Morpheus. The team has decades of background in strategy, analytics, and system design having advised some of the largest companies in the world before focusing more exclusively on Web3 entities. The team has been active in the Web3 environment for many years and has extensive experience working alongside all different types of companies.

## Status
In Discussion

