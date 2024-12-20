# MRC47 Distribution of Historical Builder Reward MOR Tokens Stored in the Smart Contract
## Authors: Smart Agents
## Status: Implemented

## Context
- Since February 8th 2024 the MOR emissions for Builder Rewards have been building up in the Distribution Smart Contract.
- As of September 28th 2024 a total of 790,891 MOR have been emitted and held in the Smart Contract.
- Statistics from https://morlord.com/ 
- When Builder Rewards go live, new emissions will start being rewarded to builders based on that Smart Contract logic.
- There is no existing proposal either in the white paper or elsewhere in Docs repo that addresses how to distribute these previous MOR held in the Smart Contract.

## Objective
Develop system for the distribution of Builder Reward MOR token that has been stored in the Smart Contracts since launch.

## Proposal Details
- Identify existing "Builders" who created Frontend / User Facing Applications, Smart Agents, and other projects that qualify for these historical MOR Builder tokens.
- When MOR Builder Rewards become claimable in December 2024, then begin distributing these MOR to identified Builders.
- The distribution period should be weighted based on how long the Builder has been contributing, toward an average of 30 months.
- 30 month period is reflective of the real world 36 month average that has emerged for Capital & Coding Staking minus the 6 month non Staking time period.
- The contribution period should count time both before and after Builder Rewards go live.
- For example contributor A was acting as a Builder for 16 months then their Distribution period equals 14 months. 

Stats from: https://mor-explorer-frontend.pages.dev/staking
![3YearAverage](https://github.com/user-attachments/assets/59c0a399-d63b-4044-bf08-c6b49e8b763d)

## Criteria and Logic For Builders Rewards Distributions
- Existing utility offered to Morpheus users beyond what has been contributed to the Reference Implementations.
- Examples: Mor.org, Morlord.com, Venice.AI, Lumerin Compute Dashboards, MORAgents Smart Agent Builder Tools.
- Ranked by usage by users. For example Mor.org is the top ranked Morpheus related website when you search for Morpheus on Google.
- Based on historical contributors to Community websites and applications before this MRC was created (to avoid gaming).
- Review utility to the Morpheus community across Smart Agent Builders, Compute Providers, Capital Providers, and Code Providers.
- Builder Contributions should be maintained during the 18 months of the distribution period to receive full distribution.

## Tool for Distribution
Well developed tool for distribution of tokens over a defined time period.
https://sablier.com/

## Coding
No new coding is required to implement this MRC. 

## Timing
The analysis should be complete before the Builder Rewards go live (which is anticipated to be at the same time as the Compute Rewards).

