# MRC34: Smart Agent Domains

Author(s): ArtemUpnode, Chomtana, upnodedev  
Category: [MRI1](https://github.com/MorpheusAIs/SmartContracts), [MRI9](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC08.md)

## Summary

Smart agent domains identify smart agents (NFAs) and solve the problem of how frontend UIs and developer tooling interact with smart agents. Users will be able to access smart agents by entering their domains in clients/bots and other AI platforms, which provide an easy-to-use interface for each agent. And developers using domains will be able to easily interact with smart agents through common interface.

## Rationale

Besides simplifying user-to-agent and tooling-to-agent interactions, this also improves interaction between Morpheus components and future integration with other third-party tools (e.g. [ComfyUI](https://github.com/comfyanonymous/ComfyUI), [Botpress](https://botpress.com/th), [Zapier](https://zapier.com), [Node-RED](https://nodered.org), etc).

Agents domain name: `AgentName.mor` (mor stands for Morpheus).

Example of user-to-agent and tooling-to-agent interaction,

![interaction](https://github.com/ArtemUpnode/MRC/assets/167774506/53e6c5b9-98ca-465d-81ed-811d5d637c34)

The solution will be related to the [Morpheus Lumerin Model](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Morpheus%20Lumerin%20Model.md), [NFA (MRC21)](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC21.md) and [MOR Staking (MRC22)](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC22.md). Details:

- Domain name is optional for the agents, just like ENS domains
- Domain name is reserved by staking MOR, making domain more unique and valuable
  - Best conditions for staking (locks, fees, term, etc) TBD
  - Domains can be either affordable to many (small minimum staking), or expensive, which in turn can make them more trusted and desirable to agent developers (UNDER DISCUSSION)
    - In the first case, the availability of domains simplifies interaction even with unpopular agents
    - In the second case, when domains are available to agents with a large amount of staking from users it adds motivation for developers to attract staking to their agent
- In agent-to-agent interactions, the domain may also provide access to Inference on Morpheus (due to staking MOR)
- Domains marketplace with auction system in the future

Example of simple integration of smart agent (NFA) and third-party tools,

![integration](https://github.com/ArtemUpnode/MRC/assets/167774506/a67aa20f-dca3-4f8e-961e-68c4cde5723e)

> The Agent struct is taken as an example from the Lumerin Model, for NFA it will be ERC-721 with the necessary data for interactions (Agent Abi, etc).

This MRC can be part of the Morpheus Lumerin Model, MRC21 and MRC22. However, we believe it would be better to separate complex projects into parts.

## Value Proposition

Domains simplify interaction and integration, adding a unique naming element familiar to many Web3 users. This represents an additional use case for the MOR token, and such an ecosystem approach will also incentivize developers within the [Waterloo Community Apps Builder Model](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC08.md).

Moreover, we are developing the registry smart contract essential for implementing the [MRC25](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC25.md) global naming system. By placing a paywall in front of domain name registration, this system further strengthens the utility and value of the MOR token. Our team has pioneered the "stake to reserve" model for the first time, aligning it with the [Waterloo Community Apps Builder Model: MOR Staking - A Free Market Mechanism To Direct MOR Rewards Toward End User Applications](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC08.md#1-mor-staking---a-free-market-mechanism-to-direct-mor-rewards-toward-end-user-applications).

Additionally, we are researching publish-subscribe interoperability. The smart agent information stored in our registry will be interoperable across any chain by leveraging our common infrastructure. For example, our tech can be used to enable relaying of data in original registry across chains.

We will soon publish an analysis of our domain name's impact on the value of the MOR token.

We also help blockchains, ecosystems and other third-patry platforms such as workflow editors and automation platforms integrate smart agent domains through our standard. Without smart agent domains, the absence of a common interface could lead to chaotic integrations and diminish the likelihood of collaborating with major platforms.

### Use Case Research

Here are platforms we have evaluated and are considering for integration,

#### ComfyUI

Powerful and modular stable diffusion GUI and backend, the ui of which allows design and execution of advanced stable diffusion pipelines using a graph/nodes/flowchart based interface. Smart agent domains adds convenient integration with ComfyUI to create complex Stable Diffusion workflows.

#### Zapier

Zapier allows you to connect popular services such as email and Google Forms with other services. Smart agent domains enable Zapier to link these services to the smart agent.

#### Botpress

Botpress allows you to create a chatbot with a custom workflow. We can include a smart agent domains block to facilitate integration with smart agents.

#### Node-RED

Node-RED is an open-source, workflow-based programming platform used by enterprise companies. It is primarily employed in the IoT field to define logic that synchronizes data between cloud servers and various sensors and devices. However, Node-RED's capabilities are not confined to IoT applications alone; it can be adapted for use in any field, including AI and smart agents.

## Dependencies

[Morpheus Lumerin Model](https://github.com/MorpheusAIs/Docs/blob/main/!KEYDOCS%20README%20FIRST!/Morpheus%20Lumerin%20Model.md), [MRC21](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC21.md), [MRC22](https://github.com/MorpheusAIs/MRC/blob/main/IN%20PROGRESS/MRC22.md) and [MRC26](https://github.com/MorpheusAIs/MRC/blob/main/MRC26.md).

We depend on these implementations, but are not strictly limited to them. If necessary, missing implementations will be developed by our efforts within this MRC.

## New Weights Requested

TBD.

## Existing Weights

None.

## Deliverables

Expected deliverables are described in Value Proposition and Rationale. May vary due to Dependencies.

## Background

### Team Members

- upnodedev - Project Manager
  - [TMKMS YubiHSM Installer Interactive Shell](https://github.com/upnodedev/tmkms-yubihsm-install-shell)
  - [OP Stack open-source docker compose deployment](https://github.com/upnodedev/opstack-compose)
  - [op-erigon-docker-compose](https://github.com/upnodedev/op-erigon-docker-compose)
  - [Celestia Rollup Demo: Celestia Domains](https://github.com/upnodedev/celestia-domains)
  - [Celestia Node and Validator ansible installation script with interactive shell](https://github.com/upnodedev/celestia-ansible)
- Artem - Backend Developer
  - [Forking of Keplr wallet to integrate YubiHSM2 support](https://github.com/quertc/keplr-wallet)
  - [Celestia blob submission UI](https://github.com/quertc/celestia-ui)
  - [OP Stack open-source docker compose deployment](https://github.com/upnodedev/opstack-compose)
- Chomtana Chanjaraswichai - Smart Contract Developer
  - [Optimism TechNerd](https://github.com/orgs/ethereum-optimism/projects/31/views/1?pane=issue&itemId=56338540)
  - ENS Contributor (see below)
  - [Opti.domains](https://opti.domains)
  - [RetroList](https://retrolist.app)
  - [simple-optimism-node](https://github.com/Chomtana/simple-optimism-node)
  - and more...
- Kittikorn Keeratikriengkrai - Frontend Developer
  - [RetroList](https://retrolist.app)
  - [Inspex Lighthouse](https://app.inspex.co/lighthouse)
- Poonpetch Luancharoen - UX/UI Designer
  - [RetroList](https://retrolist.app)
  - [Inspex Lighthouse](https://app.inspex.co/lighthouse)

### ENS Contributions

- [Contributed to the development of the ENS Official OP CCIP Gateway, post-fault proof merge, which disrupted prior implementations](https://github.com/ensdomains/evmgateway/pull/36)
- [Open a discussion on the ENS DAO Forum for the above contribution](https://discuss.ens.domains/t/op-fault-proof-upgrade-break-op-verifier-and-op-gateway-implementation-in-the-evm-gateway/18973)

### Grants

- [Opti.Domains - Superchain Domains Development - OP Grantee Cycle 11](https://gov.optimism.io/t/ready-gf-phase-1-proposal-opti-domains-interoperable-domain-name-for-the-op-stack/5510)
- [Opti.Domains - OP RetroPGF 3](https://retrolist.app/project/0x633cd3fb8c979e5a98b2fc44c86d0d2003bca6359600731fc0f6a0dd9c3e7981)
- [Add custom UniversalResolver support to Wagmi - ENS Small Grants Ecosystem Round 9](https://ensgrants.xyz/rounds/29/proposals/708)
- [Opti.Domains | Scale ENS to OP - Gitcoin ENS Identity](https://explorer.gitcoin.co/#/round/42161/24/32)

## Status

UNDER DISCUSSION
