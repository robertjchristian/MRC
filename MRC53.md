## MRC 53: Add Block Reward Emitted to Compute Subnets To Bootstrap Usage

### Status: **Proposal**

**Summary:** 
Today MOR emissions to Compute Subnets are based 100% on usage of AI models / agents as recorded in "sessions" between a Subnet and a user that opens the session. Without a block reward, their is a cold start problem where not enough Compute is being offered at a low price to attract Inference users to access the Morpheus Compute. This proposal is to introduce a "block reward" split between Compute Subnets based on the number / length of sessions they host, only limited by the amount of MOR Staked toward their Subnet. The intent is to increase the incentive for Compute Subnets to compete for these generous emissions of MOR and thus bootstrap the network into a robust number of Compute Subnets, Stakers, and users.

## Emissions Model: 
https://docs.google.com/spreadsheets/d/1gUV5r-ERVBLbF0dHLl66NXtKU6K2WxtUhoflT_o4mbM/edit?usp=sharing

## V2 of Compute Emissions Smart Contract with Block Reward modeled after Builders Style Staking System + Compute Sessions

## Step 1. Changes to Existing Compute Smart Contracts to start Compute usage competition:
The existing Compute Smart Contract does most of the functions required for this updated version. The functions of Staking MOR or paying MOR to open sessions will all stay the same. The main aspect that will be updated is to compare the total sessions of all Subnets to generate a "weight" for each Subnet.

**Functions:**
- The Smart Contract records the number of Compute sessions each Subnet provides during a fixed period (1 day) as a "weight".
- The Smart Contract records the of sessions per day for ALL sessions provided by all Subnets and calculates their "total weight".
- This Smart Contract calcualtes the percentage of weight for each Subnet based on their weight divided by the total weight. 

- Example: 100 sessions provided by Subnet XYZ out of 1,000 sessions hosted by all Subnets on March 15th.
Thus 10% of the block reward goes to Subnet XYZ.
3,254 daily emissions go to Compute Subnets.
10% of 3,254 equals 325 MOR rewarded for the daily period to Subnet XYZ.

## Step 2. Staking Alignment Check via Compute Smart Contract Modeled on Builder Type Staking
The existing Builder Smart Contract has all the logic for users Staking toward Subnets and rewarding MOR emissions on this basis. The change for Compute will be to simply pull these emissions from the Compute pool instead of the Builder one.

**Formula:** Amount Staked divided by total Compute MOR emitted since February 8th 2024.
- Example: 120,000 divided by the 1,200,000 equal 10% of 3,254 MOR per day.
- Maximum Distribution: After staking equals aggregate amount emitted the total Compute pay out will be equal to the daily emissions of 3,254 to compute providers in proportion to their stake within the compute bucket.

## Calculator Smart Contract 
This new Calculator Smart Contract will look at the MOR emissions earned by Subnets from Step #1 as the maximum MOR it can recieve and check the amount from Step #2.
If the amount of MOR Staked in Step #2 by Subnet XYZ are equal to or greater than the MOR available from Step #1 then ALL MOR credited in Step #1 are issued to the Subnet.
If the amount of MOR Staked is Step #2 by Subnet XYZ are less than the MOR available from Step #1, then only the amount of MOR credited in Step #2 are issued to the Subnet.

**Conclusion:**
This model creates a robust competition between Compute Subnets to open lots of sessions with users, but caps their MOR emissions to the amount of MOR they have Staked to their Subnet. Thus anyone creating synthetic sessions will at a minimum be creating demand for MOR via Staking greater than their potential rewards over 1 year, as APY on Compute Staking will start at around 75% APY.

## Additional Notes:
This means that there will be three ways to earn MOR as a Compute Subnet.
1. Compute emissions Proportional to the Staked MOR block reward / usage.
2. Compute Treasury pays emissions for usage of Compute sessions in addition.
3. Compute Smart Contracts / Router allows for direct payments of MOR for a session in addition.

## Benefits: 
1. Design allows for current Smart Contracts to stay the mostly same as deployed for payments of MOR based on usage and direct payments of MOR.
2. The Compute Smart Contract for Staking based MOR emissions is very similar to Builders V2 Smart Contract. With the only change being the pool ID the MOR is emitted from.
3. Thus only one new Smart Contract is required to do the calcuation of the usage weight & the Staked amount.
