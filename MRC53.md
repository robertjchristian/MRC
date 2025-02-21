## MRC 53: Add Block Reward to Compute Emissions "Minimum Daily Emissions"

### Status: **Proposal**

## Emissions Model: 
https://docs.google.com/spreadsheets/d/1gUV5r-ERVBLbF0dHLl66NXtKU6K2WxtUhoflT_o4mbM/edit?usp=sharing

## V2 of Compute Emissions Smart Contract with Block Reward modeled after Builders Style Staking System + Compute Sessions

## Proof of Work via AI Compute:
- Subnet has to show Compute sessions.
- Calculate number of sessions per month and make the additional block reward proportional to the sessions hosted by the subnet.

## Staking Alignment Check:
- Formula for Emissions Distributions: Amount Staked divided by total compute emitted.
- Example: 120,000 divided by the 1,200,000 equal 10% of 3,254 MOR per day.
- Maximum Distribution: After Staking equals aggregate.amount emitted to distribution  date. After staking equals aggregate amount emitted the total Compute pay out will be equal to the daily emissions of 3,254 to compute providers in proportion to their stake within the compute bucket.

## Three ways to earn MOR as a Compute Provider
1. V2 Compute emissions Proportional to the Staked MOR.
2. V1 Compute pays emissions for usage of Compute sessions in addition.
3. V1 Compute allows for direct payments of MOR for a session in addition.
4. Calculation Contract that looks at Sessions and Staking to figure out total emissions to each Compute Subnet.

## Benefits: 
1. Design allows for current Smart Contracts to stay the mostly same as deployed for payments of MOR based on usage and direct payments of MOR.
2. The Compute Smart Contract for Staking based MOR emissions is a copy and paste of Builders V2 Smart Contract. With the only change being the pool ID the MOR is emitted from.
