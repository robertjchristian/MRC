# MRC 36 - Rewarding long-term committed contributors

Author(s): Mechaverse

Category: [MRI1](https://github.com/MorpheusAIs/SmartContracts)

## Summary

The MRC 36 proposes a mechanism to reward contributors who are willing to commit to the long-term success of the Morpheus project. By allowing contributors to voluntarily lock their MOR tokens for a predetermined period, they can receive an increase in the amount of MOR rewarded. This incentivizes long-term commitment and helps stabilize the ecosystem by ensuring that contributors with a vested interest in the project's success are recognized and rewarded proportionally.

## Rationale

This proposal aims to enhance the commitment of Morpheus contributors by introducing a system that rewards those who demonstrate long-term confidence in the project. 

### Option 1 - Locking claiming rights:

 - A contributor voluntarily locks his claim rights for a period of time.
 - The system applies a multiplier to the contributor's weights, capital, or any other contribuiton metrics, thereby increasing their participation in the pool during the lock-in period.
 - The MOR received comes from the 24% pool reserved for contributors group. 
 - No new MOR is created nor are the current emission rules changed. There is only a change in the contributor's share of the pool.

A formula could start by setting a minimum and a maximum locking time. For example, projects such as Curve allow locking from 4 weeks to 4 years to obtain veCRV.

Let's assume that a minimum of 4 weeks and a maximum of 4 years is a reasonable duration. A multiplier can be calculated using the following simple formula:

- **Multiplier =  Number of weeks locked / 104 weeks.**

And the new contribution indicator for calculating the new quota would be as follows:

- **New contribution indicator = base contribution indicator + base contribution indicator * Multiplier**

So someone locking tokens for 1 year would receive a 50% bonus. 2 years, 100%.  4 years 200%.

#### Example for a Code Contributor

- 100 weights have been given to all contributors.
- Joe has 1 weight, so he receives 1% of the Code group's emissions.
- Joe decides to lock his claim for 2 years.
- Applying the formula, his new contribution indicator is 2 (1 + 1*(104/104)).
- Joe now receives 2% of the Code Group's emissions but will not be able to claim his MORs for another 2 years.
- All other contributors have been slightly diluted.

The same example could be applied to the Capital contributors group by changing "weight" to "stETH".


#### Benefits

 - It is a solution that can scale to any group of contributors.
 - It appears to be a moderately complex form to implement.
 - The fact that it is a multiple is also interesting to deal with the case where a contributor stops contributing. By losing the base contribution indicator , he would also lose the bonus. In other words, locking the tokens and ceasing to contribute could also lead to the loss of the bonus.
 - Similarly, the contributor could continue to contribute and the new weights received or capital contributed would also be boosted by the multiplier.
   
#### Challenges

 - As MOR is not claimable, it cannot be used for staking as described in MOR22.
 - Nor can it be used to make inferences.

Below I propose a way to solve these problems.


### Option 2 -  Locking claimed MOR tokens:

 - A contributor claims his tokens
 - It then locks them for a period of time on another smart contract. 

#### Benefits

 - This system can be applied on already claimed MOR.
 - This system can be applied by any user with MOR.

#### Challenges

- It appears to be more complex to implement than option 1.
- It is difficult to agree where the new MOR emissions come from: Fees from the Uniswap pool? Part of the protection fund? Donation from each group to create a fifth group?
- The commitment message that may emanate from this action is weaker as there is no lock-in of future emissions.


### Solution to the use of MOR utilities

By locking access to MOR tokens, it could be blocking staking as described in MOR22 or the use of its inference rights.

One solution could be inspired by the one used by the Curve system with veCRV. Users can still vote and earn returns but cannot transfer them because there is no veCRV token itself (although there is a unit of veCRV accounts within the Curve system).

Taking inspiration from this solution, we could keep the utilities of locked MORs by simply looking at the amount of MORs that a wallet has locked.

In this way:

- MOR utilities can still be used within the Morpheus ecosystem while keeping tokens locked.
- Once unlocked, these tokens are no longer taken into account until they are used in the standard way.


### Conclusions

The two proposed options appear to be complementary and to pursue slightly different purposes.

Option 1 is better defined and apparently presents a less intrusive implementation. Moreover, the message emanating from its use is clear and powerful: "As a Morpheus contributor, I am committed to being involved in the project over time". It generates great trust in the community and brings honour to the contributor.

Option 2 is interesting to offer a lock-in option to all MOR holders. It could also be an option to develop another type of utility for MOR token. It would be necessary to define the origin of the additional MOR obtained.


## Value Proposition

The proposed system will significantly enhance the value Morpheus provides to its contributors and users. By incentivizing long-term commitment, the system ensures that the most dedicated and confident contributors are rewarded for their loyalty and belief in the project. This leads to a more stable and motivated contributor base, which in turn drives higher quality contributions and continuous improvements to the ecosystem. Additionally, by publicly demonstrating their long-term commitment, contributors can build greater trust within the community, attracting more users and contributors who are aligned with the project's long-term vision. Ultimately, this system strengthens the overall stability and growth potential of the Morpheus ecosystem.

## Dependencies

None.

## New Weights Requested

TBD.

## Existing Weights

None.

## Deliverables

1. Updated Smart Contract: A modified Morpheus Smart Contract that includes the functionality to allow contributors to lock their MOR tokens for specified periods and to track these locks.

2. Weight Calculation Mechanism: A new or enhanced algorithm that accurately calculates and allocates additional weights to contributors based on the amount of MOR locked and the duration of the lock.

3. User Interface Updates: Modifications to the Morpheus user interface to provide contributors with the ability to lock their MOR tokens, view their locked tokens, and see the additional weights they have earned.

4. Documentation: Comprehensive documentation detailing the new system, including guidelines for contributors on how to use the reward boost system, technical documentation for developers, and updates to the existing Morpheus protocol documentation.

5. Testing and Validation: A complete suite of tests to ensure the new features work as intended, including unit tests, integration tests, and user acceptance testing. Validation of the system's security and reliability will also be conducted.

6. Deployment Plan: A detailed deployment plan outlining the steps to roll out the new features, including a timeline, risk assessment, and mitigation strategies.

## Implementer

Open to anyone able to implement it. The author will act as facilitator.

## Status

UNDER DISCUSSION
