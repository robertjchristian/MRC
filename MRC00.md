# MRC 00: Morpheus Request for Comment (MRC)  Introduction
MRC, meaning Morpheus Request for Comments, is integral in suggesting and executing changes within the Morpheus ecosystem. This document is designed to make the submission process more transparent, fair, and efficient.

## Purpose and Scope
This guide is crafted for contributors and users within the MOR ecosystem, facilitating structured proposals for standards and material changes to one of the ten [Morpheus Reference Implementations.](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Reference%20Implementations.md) If you are seeking to build a Smart Agent and deploy it on Morpheus, no MRC required, just register it on MOR.Software and enjoy.

## Submission Timeline and Platforms
Proposals are welcome on GitHub during the Fair Launch phase, eventually moving to MOR.Software for broader community interaction.

Writing a Well-Formed MRC To draft a compelling MRC, study existing examples to grasp the expected format and substance. Use the provided templates for standards and changes to Morpheus structure your proposal.

## Standard Information to Include
An MRC must encompass specific details based on its type of proposal, as detailed in the subsequent templates.

## MRC Request Template
* Title: MRC#### - [Title of the Funding Request] - [Category]
* Author(s): [Author Name(s) and Discord Handle(s)]
* Category: [refer to Categories below]
* Summary: Concise summary of the initiative.
* Rationale: Importance of the project and why it merits acceptance, including a simple solution description, delivery strategy, and technology stack.
* Value Proposition: How will the project tangibly increase Morpheus's value to users?
* Dependencies: Other MRCs or tasks needing completion beforehand.
* New Weights Requested: Number of weights. [See guide here.](https://github.com/MorpheusAIs/Docs/blob/main/Guides/Code%20Contributor%20Weights%20Guide.md)
* Existing Weights: Current weights of features or code your proposal will enhance.
* Deliverables: Detailed account of what the project will deliver.
* Why You?: Your or your team's credentials for executing the proposal.
* Status: Current state of the proposal (Discussion, In Progress, Implemented).

## Submission Guidelines
Properly document your MRC in the repository and list it in the README for community review. Fork the relevant template and select the most pertinent category.

## Select the Affected Category
Choose the category matching the MRI your MRC impacts. Reach out to [SmartAgents] if you're uncertain about the category fit.

## [Morpheus Reference Implementation (MRI) Categories](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Reference%20Implementations.md) 
### Smart Contracts: Changes to Morpheus smart contracts.
- Maintainer's Discord Handle: smartagents
- Link to Repo: https://github.com/MorpheusAIs/SmartContracts
### Smart Agent Tools & Examples: Development and deployment aids for smart agents.
- Maintainer's Discord Handle: lachsbagel
- Link to Repo: https://github.com/MorpheusAIs/SmartAgents
### Morpheus Local Desktop/Mobile: Desktop and mobile application proposals.
- Maintainer's Discord Handle: scott_b_
- Link to Repo: https://github.com/MorpheusAIs/Morpheus
### TCM / MOR20 (Token and Financial Models): TCM/MOR20 standard-related proposals.
- Maintainer's Discord Handle: storm.father
- Link to Repo: https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/TechnoCapitalMachineTCM.md
### Protection Fund: Enhancements to protection funds and security.
- Maintainer's Discord Handle: storm.father 
- Link to Repo: https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Protection%20Fund%20Details.md
### Capital Proofs Extending: Capital proofs improvements.
- Maintainer's Discord Handle: smartagents
- Link to Repo: https://github.com/MorpheusAIs/MRC/blob/main/In%20Progress/MRC15.md
### Compute Proofs MOR/Lumerin: Computational proofs improvements.
- Maintainer's Discord Handle: rcondron
- Link to Repo: https://github.com/MorpheusAIs/Morpheus-Lumerin-Node
### Code Proofs and Examples 
- Maintainer's Discord Handle: scott_b_
- Link to Repo: https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Coder%20Guide.md
### Frontend Proofs & Examples: Frontend resource, proofs, and functionality enhancements.
- Maintainer's Discord Handle: erikvoorhees
- Link to Repo: https://github.com/MorpheusAIs/MRC/blob/main/MRC08.md)https://github.com/MorpheusAIs/MRC/blob/main/MRC08.md 
### Interoperability: Proposals for improving ecosystem interoperability.
- Maintainer's Discord Handle: urklan
- Link to Repo: https://github.com/MorpheusAIs/MRC/blob/main/In%20Progress/MRC16.md)https://github.com/MorpheusAIs/MRC/blob/main/In%20Progress/MRC16.md

## Meta MRCs about MRCs
- [For most MRCs in general this MRC00 is the first Meta MRC.](https://github.com/MorpheusAIs/MRC/blob/main/MRC00.md  ) 
- [For MRCs about adding new assets, yield sources, chains, see this MRC guide.](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/The%20Morpheus%20Asset%20Integration%20Framework.md)

## Life Cycle of an MRC
**- 1. The Beginning:** The MRC has to be merged into Discussion, this indicates the repo maintainer believes the MRC is at least worth discussion and has basic merit to their Reference Implementation.

**- 2. Timeline Expectations:** Maintainers should seek to review and provide feedback to MRC authors once a week. So authors can get a sense of the next steps/current state of their MRC.

**- 3. Advancing An MRC to "In Progress":** Much of the feedback to MRC authors is often about understanding dependencies and what technical hurtles exist for the MRC to be implemented.
Once all technical dependencies have been addressed, only then can an MRC be accepted into the "In Progress" stage.

**- 4. Completing / Implementing an MRC:** For the MRC to be considered complete and "Implemented" the code proposed must be contributed and merged by the maintainer.

## Acceptance / Rejection:
- First, it's important understand that MRCs are a competitive process.
Someone who proposes better implementation/lower weights/shorter timelines can be chosen (understand that submitting an MRC does not equal that MRC being accepted).

- Second, if the maintainers' feedback wasn't addressed by an author for two weeks, the MRC is considered rejected and can't be re-submitted for one month. 

- Third, a maintainer may close a MRC pull request if there is a technical hurtle that can't be currently addressed to implement the MRC, or not enough weights being available from that maintainer to accept the MRC, or the maintainer judges the MRC proposal too expensive vs the value of the change / improvement proposed.

## Competition Among MRI Repo Maintainers To Increase Decentralization
The Morpheus Atomic Governance system aims to be a free marketplace even for the Morpheus Reference Implementations themselves and thus the repo maintainers are not static but compete and are dynamic.

What this will look like in practice is:
- Anyone can start a fork of an existing [Morpheus Reference Implementation.](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Reference%20Implementations.md)
- They can set their own weights for how they choose to reward those contributing to their version of the repository.
- Their code / version of the MRI is a MRC21 Non Fungible Agent with a reward address.
- The protocol MOR emissions gauge an on chain metric to understand usage of that fork vs all other options.
- MOR rewards are sent accordingly (as part of the 24% Coding bucket).
- This on chain mechanism could leverage a lot of the [MOR Staking on chain signaling already being developed.](https://github.com/MorpheusAIs/MRC/blob/main/MRC22.md )
- If MOR token holding does end up being the mechanism for Signaling then a free market will develop for MRIs.
- This structure leaves the MRI system open for new forks, new contributors, and free competition over time.
- Instead of ending up with 1 version the Morpheus network will have multiple competing versions.

