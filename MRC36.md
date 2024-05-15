# MRC 36 - Contributor's Reward Boost System

Author(s): Mechaverse

Category: [MRI1](https://github.com/MorpheusAIs/SmartContracts)

## Summary

The MRC 36 - Contributor's Reward Boost System proposes a mechanism to reward code contributors who are willing to commit to the long-term success of the Morpheus project. By allowing contributors to voluntarily block their MOR tokens for a predetermined period, they can receive an increase in the amount of MOR rewarded. This incentivizes long-term commitment and helps stabilize the ecosystem by ensuring that contributors with a vested interest in the project's success are recognized and rewarded proportionally.

## Rationale

This proposal aims to enhance the commitment of Morpheus code contributors by introducing a system that rewards those who demonstrate long-term confidence in the project. 

### Option 1 - Locking claiming rights:

 - A contributor voluntarily blocks his claim rights for a period of time.
 - This contributor receives additional weights proportional to the time blocked.
 - The MOR received comes from the 24% pool reserved for code contributors. 
 - No new MOR is created nor are the current emission rules changed. Only the redistribution is modified as the only modification is an increase in the number of weights of the one who blocks.

A formula could start by setting a minimum and a maximum blocking time. For example, projects such as Curve allow blocking from 4 weeks to 4 years to obtain veCRV.

A similar range could be defined and based on this, a multiple could be obtained to apply to the base weights assigned to that wallet.

A simple formula could be Number of weeks locked / 104 weeks.

So someone blocking tokens for 1 year would receive a 50% bonus, 2 years 100% and 4 years 200%.

The fact that it is a multiple is also interesting to deal with the case where a contributor stops contributing. By losing the base weights, he would also lose the multiple. In other words, locking the tokens and ceasing to contribute could also lead to the loss of the multiple.

#### Benefits

 - Few changes to the smart contract are required. The functionality to block claims is already available. The weight system is already in production.

#### Challenges

 - As MOR is not claimable, it cannot be used for staking as described in MOR22.
 - Nor can it be used to make inferences.
 - This system can only be implemented in the Code group as it is the only one that bases the distribution of new MOR issues on the weight system.


### Option 2 -  Locking claimed MOR tokens:

 - A contributor claims his tokens
 - It then blocks them for a period of time on another smart contract. 

#### Benefits

 - This system can be applied to any user with MOR. It can therefore be used by any group.

#### Challenges

- The commitment message that may emanate from this action is weaker as there is no lock-in of future emissions.
- A new smar contract and a different dynamic should be created.
- It is difficult to agree where the new MOR emissions come from: Fees from the Uniswap pool? Part of the protection fund? Donation from each group to create a fifth group?


### Solution to the use of MOR utilities

One solution could be inspired by the one used by the Curve system with veCRV. Users can still vote and earn returns but cannot transfer them because there is no veCRV token itself (although there is a unit of veCRV accounts within the Curve system).

Taking inspiration from this solution but without copying it verbatim, we could keep the utilities of locked MORs by simply looking at the amount of MORs that a wallet has locked.

In this way:

- MOR utilities can still be used within the Morpheus ecosystem while keeping tokens locked.
- In option 1, the total amount that the wallet currently holds can be used as it is dynamic.
- Once unlocked, these tokens are no longer taken into account until they are used in the standard way.


### Conclusions

The two proposed options appear to be complementary and to pursue slightly different purposes.

Option 1 is better defined and apparently presents a less intrusive implementation. Moreover, the message emanating from its use is clear and powerful: "As a Morpheus builder, I am committed to being involved in the project over time". It generates great trust in the community and gives honour to the contributor.

Option 2 is interesting to offer a lock-in option to all MOR holders. It could also be an option to develop another type of utility for MOR token. It would be necessary to define the origin of the additional MOR obtained.


## Value Proposition

The proposed Contributor's Reward Boost System will significantly enhance the value Morpheus provides to its contributors and users. By incentivizing long-term commitment, the system ensures that the most dedicated and confident contributors are rewarded for their loyalty and belief in the project. This leads to a more stable and motivated contributor base, which in turn drives higher quality contributions and continuous improvements to the ecosystem. Additionally, by publicly demonstrating their long-term commitment, contributors can build greater trust within the community, attracting more users and contributors who are aligned with the project's long-term vision. Ultimately, this system strengthens the overall stability and growth potential of the Morpheus ecosystem.

## Dependencies

None.

## New Weights Requested

TBD.

## Existing Weights

None.

## Deliverables

1. Updated Smart Contract: A modified Morpheus Smart Contract that includes the functionality to allow contributors to block their MOR tokens for specified periods and to track these blocks.

2. Weight Calculation Mechanism: A new or enhanced algorithm that accurately calculates and allocates additional weights to contributors based on the amount of MOR blocked and the duration of the block.

3. User Interface Updates: Modifications to the Morpheus user interface to provide contributors with the ability to block their MOR tokens, view their blocked tokens, and see the additional weights they have earned.

4. Documentation: Comprehensive documentation detailing the new system, including guidelines for contributors on how to use the reward boost system, technical documentation for developers, and updates to the existing Morpheus protocol documentation.

5. Testing and Validation: A complete suite of tests to ensure the new features work as intended, including unit tests, integration tests, and user acceptance testing. Validation of the system's security and reliability will also be conducted.

6. Deployment Plan: A detailed deployment plan outlining the steps to roll out the new features, including a timeline, risk assessment, and mitigation strategies.

## Implementer

Open to anyone able to implement it. The author will act as facilitator.

## Status

UNDER DISCUSSION
