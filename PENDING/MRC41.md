# Title: MRC 41 "MOR Staking For Builders"
## Sub Title: "The Time & Dilution Based Power Factor Method For Calculating Proportionality of Emissions"

### Link for Discussion on Discord: 
https://discord.com/channels/1151741790408429580/1251995756332843189

### Status: 
Pending

### Authors / Discord Name: 
Anon 866, David Johnston (Smart Agents), Anton (antonb), Anon (lachsbagel), Christopher (storm.father), Jon (jonisjon), Maxwell (scott_b_), Jeff (Jabo38), Luke (lukestokes)   

### Authors of Proposals On Similar Time Related Subjects: 
- mechaverse specifically from [MRC 36](/CLOSED/MRC36.md)
- With extensive feedback and alternative proposals from: kehndry
- Builds on MRC22: [A Free Market Mechanism To Direct MOR Rewards Toward Smart Agent & End User Application Builders](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC22.md)

### Category: 
MRI #1 Smart Contracts Reference Implementation

## Rationale: Time Equals Aliegnment
To implement economic alignment of Builders, it is necessary to implement a functionality where users can specify for what period they want to Stake their MOR tokens. It is necessary to implement a functionality where users can specify for what period they want to Stake the MOR tokens, in return the user will receive an increased reputational signal to their project.

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

## Analysis & Models:
- **Emissions Curve Calculator 7.21.2024**
https://docs.google.com/spreadsheets/d/1xTY7keBdPo2Nzm35Wdmu7ngP3NVIDebR/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

- **MOR Power Table**
https://docs.google.com/spreadsheets/d/1uEjozAcnEt-IWaSsu_BbYPRMUCkbwjwv/edit?usp=share_link&ouid=108805586783812761772&rtpof=true&sd=true

## Proportionality Equestion For MOR Staking
![ProportionalityEquationMORStaking](https://github.com/MorpheusAIs/MRC/assets/1563345/da21a701-60e7-4aba-87c1-dfe9278000bd)

## Emissions Earned By Realative Power
![Emission Earned Chart 2](https://github.com/MorpheusAIs/MRC/assets/1563345/88608be1-3199-48d0-8e08-2d7de633e241)

## Example Chart
![ExampleMORPowerFactor](https://github.com/MorpheusAIs/MRC/assets/1563345/8ff10a90-cdd3-4d65-9915-59f20fc55dbf)
Presumes a July 25th 2024 start date

## Applying the Power Factor
A power factor can be applied at deposit, if the user specifies MOR Staking period. Or with a separate function on the smart contract - `StakingClaim()`.  
The MOR Staking period is specified in seconds, it can be any interval. 
When a power factor is applied, the user's "protion" of the stETH pool increases, depending on the power factor.

## Restrictions
To implement such functionality, we need to carry a number of constraints and understand the important points:

- MOR Staking period can be set by the user or administrator (for non-automatic groups) at any time;
- MOR Staking period cannot be decreased; 
- MOR Staking period can be increased. At the time of the transaction, the new multiplier will be applied.
- Until the end of MOR Staking period, the user will not be able to withdraw their MOR rewards.

## MOR Staking in Relation to Builder Rewards
- A. Projects are listed on the decentralized registry with their MOR20 or MRC21 addresses.
- B. Projects Staking of MOR rewards into the future to increase reputation ranking, the longer the higher the power factor.
- C. MOR Staking toward Project get a proportion of the total emissions from the 24% rewards to Builders.
- D. Projects added to front ends / user interfaces after passing a public audit.

### Advanced Version of MOR Staking for Builders:
- A. Staking MOR releases only after the MOR fees paid to the Morpheus Protocol Owned Liquidity exceed that of the MOR rewards paid out by the Protocol.
- B. Projects activated into front end by enough Weight holders signalling as proven by on chain record of Code Contributions.

## Changes to Smart Contracts
The Distribution contract and related interfaces will change. Updates to the smart contract on the network will need to be made.

## Timelines
10 weeks from June 21st 2024.
