# **MRC33: Future-proofing Morpheus — Wormhole NTT for MOR Interoperability**

**Category:** Interoperability: Proposals for improving ecosystem interoperability \
**MRI Reference:** [Morpheus Reference Implementation 16 — Interoperability ↗︎](https://github.com/MorpheusAIs/MRC/blob/main/IMPLEMENTED/MRC16.md)

**Discord Link: https://discord.com/channels/1151741790408429580/1230260441540722708**

---
### **Status**
**April 17th, 2024: UNDER DISCUSSION**

---

## **Summary**

The Morpheus community has demonstrated its commitment to expanding the project’s multichain capabilities, looking to make the MOR token composable across multiple blockchains as it prepares for a fully functional launch on May 8th. This presents a critical window of opportunity to make a well-informed decision on its multichain architecture, weighing potential advantages and tradeoffs between available solutions while aligning with the long term goals and core values of the Morpheus community. The decision made today will shape the future of the Morpheus protocol, influencing its security, flexibility and autonomy.

As the MOR token has not yet been launched publicly, transitioning to a different multichain framework would not require a complex migration or disrupt the timeline. While the exploration of utilizing OFT highlights benefits such as a streamlined integration and contract immutability, it is crucial that the community approach the decision with care and diligence. The framework Morpheus adopts will influence how the project can evolve and adapt to new challenges and opportunities — understanding the characteristics of the multichain infrastructures available today will ensure that the foundations built are capable of positioning Morpheus for enduring growth and success for years to come.

After consideration and analysis we present Wormhole’s Native Token Transfers (NTT) framework as a compelling alternative to LayerZero’s Omnichain Fungible Standard (OFT). NTT offers a range of benefits, including significantly enhanced flexibility, non-proprietary open source security features, and a bleeding-edge modular design that puts full ownership and control in the hands of Morpheus.

Transparent security, commitment to adapt to shifting trust minimization paradigms, and the preservation of autonomous, independent project governance are core design motivators for Wormhole’s Native Token Transfers framework. Integrating the MOR token with NTT would minimize risks and dependencies while maximizing autonomy and tapping into synergies that help pave the way for resilient multi-chain operations across the Morpheus ecosystem.

## **Rationale: Evaluating limitations of MOR as an OFT**

Integrating LayerZero’s OFT ([outlined in MRC16 ↗︎](https://github.com/MorpheusAIs/MRC/blob/main/IMPLEMENTED/MRC16.md)) presents a path forward for the multichain expansion of Morpheus. However as a community, it is important to assess whether the OFT standard aligns with the vision and values of Morpheus by evaluating its limitations and risks.

**Vendor lock-in and loss of sovereignty**



* Morpheus loses its autonomy as a token issuer by locking MOR into immutable OFT contracts
* LayerZero DVN wrapper contracts are not immutable, and are owned by LayerZero instead of by Morpheus
* This means arbitrary fees can be imposed over DVN implementations

**Security concerns and vulnerabilities**



* Lack of advanced and configurable security features, such as:
    * Inbound and Outbound rate limiting
    * Pausing
    * Access Controls
    * Accounting to maintain balance integrity across chains
* Closed source, off-chain security modules such as Pre-crime with no native verification network compounds reliance on external codebases

**Limited flexibility and unsolved UX problems**



* OFTs without DVNs are immutable and lock-in to LayerZero verification [which has low security as assessed by a independent bridge committee appointed by Uniswap ↗︎](https://uniswap.notion.site/Bridge-Assessment-Report-0c8477afadce425abac9c0bd175ca382)
* LayerZero’s OFT does not solve a major challenge with cross-chain messaging: relaying verified messages to the destination chain

**Governance challenges**



* Dependence on LayerZero governance processes may lead to conflicts in priorities, such as changes to its pricing model or roadmap
* Immutable contracts and Endpoints that are deployed and controlled by a third party limit the flexibility of the Morpheus contributors to evolve their interoperability infrastructure as their needs may change

These limitations do not preclude the use of OFT, however they emphasize the importance of assessing the long term implications of conforming to the standard. Constraints and reliance on LayerZero’s governance processes may not align with the principles laid out by Morpheus contributors. Lack of control over the OFT stack might hinder the project’s ability to incorporate new features and enhancements.

As LayerZero is a private entity there is an inherent risk that their priorities and incentives may diverge from those of the Morpheus community. Its multichain infrastructure may be subject to arbitrary fees imposed in the future not aligned with the operational costs of maintaining a verification network, as it is designed to be a wrapper around other networks.


## **Value Proposition: Why transition to the NTT framework?**

As members of a decentralized project, the Wormhole Contributors place high values on open source, transparency, and self-sovereignty. While NTT itself is a relatively new framework, it is projected to secure billions of dollars in on-chain value by the time the MOR token launches. The Wormhole Contributors therefore present an alternative available path to Morpheus with clear benefits that align with the project’s values and goals.

**Advanced security features**



* On-chain inbound and outbound rate limiting, configurable per-chain by arbitrary time periods or value transferred
* Global Accountant giving access to a full, synchronized multichain token state and enforcing isolation of balances on a per-chain basis
* Contract Pausing and Access Control between Owner and Pauser roles

**Unparalleled future-proofing**



* Customizable and transparent verifier configurations (or Transceivers) that enable m-of-n custom attestation thresholds with no arbitrary fee impositions
* Significant R&D investment into trust-minimized messaging paradigms (hardware partnership with [AMD ↗︎](https://blockworks.co/news/wormhole-zero-knowledge-amd-collab), open sourced[ zk-light clients ↗︎](https://github.com/wormhole-foundation/example-zk-light-clients) (more to come), deep technical collaborations with[ Lurk Lab ↗︎](https://lurk-lab.com/) and[ Succinct ↗︎](https://succinct.xyz/))

**Preservation of control and autonomy**



* Clear separation of cross-chain logic and the token implementation through well-defined interfaces
* No vendor lock-in: complete ownership over both MOR token and NTT contracts, fully compatible with decentralized governance processes

**Well designed multichain UX**



* NTT contracts are flexible to integrate with various kinds of message relaying mechanisms, to ensure that users are able to pay for their messages to be delivered on destination chains
* Rate limited transfers are queued so users have confidence that their transfer will go through after a certain time period

**Strong ecosystem synergies**



* NTT seamlessly integrates with Solana today, enabling MOR fungibility between EVM and SVM at launch on May 8th without the need for wrapping, whilst simultaneously enabling the use of JitoSOL for yield (outlined in[ MRC17 ↗︎](https://github.com/MorpheusAIs/MRC/blob/main/MRC17.md))
* Cross-Chain Queries ([CCQ ↗︎](https://docs.wormhole.com/wormhole/queries/overview)) can unlock other use cases for MOR with pull-based, onchain attestations of arbitrary EVM or Solana data

NTT would enable Morpheus to establish a robust, flexible and future-proof foundation for its multichain strategy while maintaining full control over its token contracts, security configuration, and governance processes. The design allows interaction without direct dependencies while aligning with the tenets of decentralization, self-sovereignty, and community-driven governance.

NTT is designed to be compatible with any existing token, and allows for free use of other verification networks with no dependencies beyond rigorously audited open source contracts, or impositions in the form of middleman fees. In its current form Wormhole’s trust assumptions are based on the decentralized coordination of 19 of the most reputable and well-known ecosystem participants and infrastructure providers in the blockchain industry, and core contracts are only upgradable via a 13/19 Guardian multisig governance process. Incentives are aligned with the priorities of integrators which in turn generate a flywheel that supports the interests of the blockchain industry as a whole, and Wormhole has demonstrated a strong commitment to pioneering a future of trust-minimized multichain message verification.

We can expect rapid advancements in best practices and challenges in security over coming years. NTT would allow Morpheus to tap directly into the sources of trust that underlie cross-chain communication in an autonomous, flexible and future-proof manner without committing to a proprietary standard.


## **Dependencies and Weights**


This MRC directly impacts the current Morpheus Interoperability architecture, however there are no direct dependencies.



* **MRI16:** [Morpheus Reference Implementation 16 — Interoperability ↗︎](https://github.com/MorpheusAIs/MRC/blob/main/IMPLEMENTED/MRC16.md)

This MRC will additionally streamline the following proposals, potentially enabling their integration before the MOR public launch.



* **MRC13:** [MOR Yield Farming on Solana with JitoSOL and/or mSOL ↗︎](https://github.com/MorpheusAIs/MRC/blob/main/PENDING/MRC13.md)
* **MRC17:** [Adding Solana Yield & MOR Token Proposal ↗︎](https://github.com/MorpheusAIs/MRC/blob/main/PENDING/MRC17.md)

We believe this MRC can be implemented before launch and audited, and estimate the technical implementation to take three days, to run the deploy scripts and set up infrastructure.



## **Deliverables: Design and Technical Implementation**


We propose the following architecture and development plan. When considering the integration of Wormhole's NTT framework into the Morpheus ecosystem, one of the key decisions is whether to adopt a pure burn-and-mint model or a hub-and-spoke approach.

Given that the MOR token is currently instantiated on Arbitrum but has not been distributed to users, the burn-and-mint approach offers several advantages including a streamlined expansion strategy that can be integrated directly into the protocol’s governance processes.

Deployment is straightforward, and Wormhole core contributors will provide close end-to-end technical support from build, testing and ongoing after launch. Should Morpheus choose to utilize Wormhole messaging, Global Accountant and Rate Limiting features can be configured directly during the integration.

![NttImage](https://github.com/wormhole-foundation/example-native-token-transfers/blob/main/images/ntt_architecture__with_custom_attestation.jpg?raw=true)


**Deploying the MOR token contracts**

On both Arbitrum and the new chains, a new MOR token contract would be deployed that implements standardized `mint` and `burn` functions, which are defined in the `INttToken` interface.

**Deploying the Manager contracts**

The `NttManager` contract would be deployed on all chains, such as Ethereum Mainnet and Solana, in `burning` mode.


* When transferring MOR tokens between chains, the `NttManager` contract on the source chain will burn the tokens, and the `NttManager` contract on the destination chain will mint the corresponding amount of tokens to the recipient

**Setting up Transceiver contracts**

If utilizing Wormhole message passing, the `WormholeTransceiver` contracts would be deployed on each chain.



* `NttManager` contracts would be configured to interact with the corresponding `WormholeTransceiver` contracts on each chain

**Registering Peers and configuring rate limits**

The `NttManager` contracts on each chain are registered as “peers” of each other.



* Desired rate limits for token transfers between each chain can be configured directly, considering factors such as liquidity, demand, and risk management

**Optional: Custom Attestations and threshold signatures**

A powerful and flexible feature of the NTT framework allows projects to incorporate additional layers of verification beyond the standard Wormhole Guardian attestations, and unlock unmatched flexibility (such as[ Lido’s NTT implementation for wstETH on BNB ↗︎](https://research.lido.fi/t/wormhole-x-axelar-lido-bridge-implementation-for-wsteth-on-bnb-chain/6012)). These supplementary verification mechanisms can enforce specific logic, security parameters, compliance requirements or unlock new bridging routes for NTT token transfers.

NTT gives the Morpheus community flexibility to utilize multiple verifiers, such as Wormhole Guardians, other bridging solutions, or its own custom verifiers (e.g. to implement custom logic as the platform evolves) providing a robust and redundant attestation process. This modular design can be configured and modified at any time, via the deployment of customized `Transceiver` contracts on each supported chain and an updating of the registry in the `NttManager` contract.


**Optional: Threshold signatures and m-of-n designs**

The framework also supports configurable thresholds for the number of verifiers required to attest to a message before it is considered valid and processed. By requiring multiple attestations, threshold signatures with an m-of-n design significantly reduce the risk of a single compromised verifier jeopardizing the entire token supply. Attackers would need to control a substantial portion of the verifiers to exploit the system. For example, a project may choose a 2-of-3 design, where two out of three verifiers must attest to a message before it is processed.


## **Background: Alignment with the Morpheus vision**

Wormhole is the world’s longest-running multichain messaging protocol and interoperability platform, with the first production message sent in August 2021. Since then hundreds of projects have leveraged Wormhole to transfer over 40 billion dollars through over 1 billion messages passed across more than 30 blockchains.

Wormhole was named the only unconditionally approved protocol by the Uniswap Foundation’s Bridge Assessment Committee (read the [Bridge Assessment Report ↗︎](https://uniswap.notion.site/Bridge-Assessment-Report-0c8477afadce425abac9c0bd175ca382) and [Full Assessment Framework ↗︎](https://docs.google.com/spreadsheets/d/1M0q__gDL6_0NQtRDkEVyBq77yZyRJdiHDpYLkHptvls/edit#gid=204785196)) and is currently undergoing its sixth Uniswap deployment — while no other incumbent interoperability platform has been utilized for more than one deployment. The wider Wormhole network is trusted and used by teams like Circle, Lido, and Synthetix.

All contracts and interfaces mentioned in this proposal have undergone several internal audits and six external audits, carried out by Cyfrin, Cantina, OtterSec, Asymmetric Research and Neodyme.

Our contributors acknowledge the value and insights gained from exploring and initiating the OFT integration process. The motivation for this MRC is rooted in identifying technical synergies with NTT that mean MOR could be seamlessly fungible across ecosystems from day one and unlock opportunities otherwise not possible as an OFT, whilst being best positioned to adapt to evolving landscapes with agility and resilience.

We believe NTT’s advanced security features, future-proof and governance-centric design, underpinned by decentralized infrastructure and incentives that are aligned with those of the wider blockchain community align with the values and interests of the Morpheus community.

NTT's design philosophy prioritizes the autonomy and sovereignty of projects, ensuring that Morpheus retains complete control over its token contracts and governance processes. This empowers the Morpheus community to make independent decisions and steer the project's direction without external influence.


## **Conclusion**

The decision to transition from LayerZero's OFT to Wormhole's NTT framework represents a pivotal moment in the multichain journey for Morpheus, and as the MOR token launch approaches it is crucial to recognize the unique advantage of this timing. By pivoting to NTT before the token release, Morpheus can establish a robust, secure, and future-proof foundation without disrupting the project's timeline or requiring migrations. We have provided a fair assessment of the rationale for transition with a transparent implementation plan, in the spirit of open collaboration and decentralized coordination.

Embracing the NTT framework opens up a world of possibilities for Morpheus. From enhanced control and flexibility to expanded use cases, the transition will cement MOR with technically independent multichain foundations and position Morpheus as a pioneer in the interoperability space.

We thank the Morpheus community for your attention and invite you to engage in open discussion, provide feedback, and contribute to the collective decision-making process. Through collaboration and forward-thinking leadership we can chart the best path forward.
