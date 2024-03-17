# Capital contracts expansion to stMATIC  

## Executive Summary
Project Name: Capital contracts expansion to stMATIC
Requesting Organization/Individual: Mor Labs 

Summary: This project aims to extend the Morpheus ecosystem to include support for Polygon, specifically for stMATIC holders, leveraging the success of Morpheus Capital Contracts with stETH. Our objective is to enhance capital contribution options within the Morpheus ecosystem, integrating high-yield opportunities from stMATIC and leveraging the chain-agnostic nature of Morpheus to foster a more inclusive and versatile DeFi landscape.

## Introduction
Mor Labs is a new guild that has formed from within the Morpheus ecosystem. Our team comprises blockchain developers, DeFi strategists, and security experts. 

To enhance the robustness and scalability of the Morpheus ecosystem, we propose the development of a comprehensive framework for integrating new capital assets. This framework aims to standardize the evaluation and integration process for new assets, starting with stMATIC, and will serve as a blueprint for future asset additions. 
The continuous evolution of the DeFi landscape presents opportunities for the Morpheus ecosystem to integrate diverse capital assets, enriching the platform's offerings and potential for yield generation. To capitalize on these opportunities systematically, a standardized framework for asset integration is essential. This approach not only simplifies the process but also enhances transparency, objectivity, and trust among participants.

## Framework for New Capital Assets Integration
The proposed framework will outline the necessary steps and considerations for integrating new staked assets into the Morpheus ecosystem. While specific details may vary based on the asset's unique characteristics, the framework will include the following core components:

- Staked Asset Identification - Description of the asset to be staked, including its relevance to the Morpheus ecosystem.
- Underlying Asset Analysis - Examination of the underlying asset, including its utility, market cap, and role in its respective blockchain ecosystem.
- Network Evaluation - Assessment of the blockchain network on which the staked asset exists, focusing on its security, scalability, and interoperability with the Morpheus ecosystem.
- Yield Mechanism Description - Detailed analysis of how yield is generated from the staked asset, including any associated risks and rewards.
- Lockup Period Considerations - If applicable, evaluation of the lockup period for the staked asset and its implications for liquidity and yield generation.
- Contract Audits and Auditors - Review of any smart contract audits conducted on the staking mechanisms, including details of the auditors and any findings.
- Market Cap and TVL Analysis - Analysis of the underlying asset's market cap and the total value locked (TVL) in the staked asset, providing insights into the asset's stability and potential for yield.
- Liquidity Evaluation - Examination of the staked asset's liquidity on primary exchanges and within the Morpheus ecosystem, assessing how it impacts overall ecosystem liquidity.
- APY Calculation - Calculation of the annual percentage yield (APY) for the staked asset, including any variable factors that may affect yield over time.
- Network Oracle Integration - Consideration of how network oracles will be used to provide accurate, real-time data for the staked asset, ensuring the integrity of yield calculations and asset valuations.

This framework is intended to be dynamic, allowing for adjustments and updates as the DeFi landscape evolves and new insights emerge. By adhering to this structured approach, the Morpheus ecosystem can ensure that all new assets are evaluated thoroughly and integrated in a manner that aligns with our strategic objectives, risk tolerance, and community expectations.

## Polygon/stMATIC addition

Polygon has successfully deployed features of Polygon 2.0, including the zkEVM, which is a milestone in leveraging zero-knowledge proofs for enhanced scalability and privacy on the Ethereum blockchain​​​​. Polygon's deployment of zkEVM as part of Polygon 2.0 highlights its leadership in zero-knowledge research and implementation. This technology is pivotal for enhancing transaction efficiency and privacy, making it highly relevant for decentralized applications, including those in decentralized AI (DeAI)​​​​. Zero-knowledge proofs, particularly as implemented in Polygon 2.0's zkEVM, offer a way to process transactions and data interactions securely and privately. This is crucial for DeAI applications, where the need to protect sensitive data while ensuring scalability and efficiency is paramount. The ZK proofs enable these applications to verify the correctness of data without revealing the data itself, thus maintaining privacy and security​​.

Given Mor Labs expertise in smart contract development and cross-chain integrations, we are uniquely positioned to undertake the expansion of the Morpheus ecosystem to support Polygon and stMATIC.

Applying the above framework for stMATIC on the Morpheus ecosystem, we can outline the required details based on the broader framework for new asset integration as follows:
Staked Asset Identification: stMATIC represents staked MATIC tokens within the Lido on Polygon system, providing users with a liquid token that can be used across DeFi applications on both Ethereum and Polygon networks. It's designed to allow users to stake MATIC tokens without locking assets or maintaining staking infrastructure, enabling participation in on-chain decentralized finance with their staked assets.


## Underlying Asset Analysis: The underlying asset, MATIC (soon to be replaced on a 1:1 basis with POL), is the native token of the Polygon network, known for its scalability and efficiency in processing transactions on the Ethereum blockchain. The market cap and TVL of MATIC would provide insights into its stability and potential for yield. As of the latest data, the staked amount in the Lido on Polygon system is substantial, indicating a healthy participation level and confidence in the staking mechanism
- Network Evaluation: Polygon (previously Matic Network) is a protocol and a framework for building and connecting Ethereum-compatible blockchain networks. It enhances Ethereum's scalability and interoperability, making it an attractive network for a variety of decentralized applications, including those in decentralized finance and AI.
- Yield Mechanism Description: Staking with Lido on Polygon allows users to earn MATIC staking rewards while maintaining full control and transferability of their assets. The staked MATIC tokens are delegated across Polygon validators part of the Lido on Polygon, with stMATIC representing the staked MATIC. Liquid staking protocols like Lido on Polygon facilitate earning staking rewards without locking assets or maintaining staking infrastructure
- Lockup Period Considerations: The waiting period for withdrawing staked assets is approximately 3-4 days, ensuring liquidity while participating in staking rewards programs
- Contract Audits and Auditors: Details about audits for the staking mechanisms are available on the Lido and associated GitHub repositories
- Market Cap and TVL Analysis: The total value locked (TVL) in stMATIC and the underlying asset's market cap provide insights into the asset's stability and potential for yield. As of the latest available data, the staked amount and the rewards paid indicate active participation and a significant amount of assets under management. At the time of writing (15th March 2024), 134,021,866 MATIC has been staked and 13,299,493 MATIC have been paid out as rewards (source) 
- Liquidity Evaluation: stMATIC can be traded on centralized and decentralized exchanges, and it can be used in liquidity pools on both Ethereum and Polygon networks, indicating a healthy liquidity profile for the asset. The Uniswap V3 pool for stMATIC can be seen here. 
- APY Calculation: The Annual Percentage Yield (APY) for staking MATIC through Lido on Polygon is approximately 4.3%, calculated based on historical on-chain data and the average return over the past 30 days.
- Network Oracle Integration: The integration with network oracles for real-time data provision was not explicitly mentioned in the sources, but the accurate calculation of APY and the use of decentralized finance applications suggest the use of reliable data sources for asset valuation and yield calculation

This framework ensures a systematic and transparent approach to evaluating and integrating new staked assets into the Morpheus ecosystem, with stMATIC serving as a prime example of how assets are assessed based on various critical parameters. 

## Problem Statement
Despite the growth of the Morpheus ecosystem, stMATIC holders currently lack the ability to contribute capital and earn rewards, thus limiting the growth of the Morpheus ecosystem of contributors and capital. Additionally, high fees on Ethereum mainnet are prohibitive for those seeking to contribute smaller amounts of capital.

## Project Objectives
The integration of stMATIC into this forward-thinking Morpheys ecosystem not only broadens capital contribution options but also places the project at the forefront of blockchain technology's evolution towards more secure, private, and efficient systems.
- Enable stMATIC Contributions: Integrate stMATIC as a capital contribution option in the Morpheus ecosystem
- Dashboard Integration: Update the Morpheus dashboard to support Polygon L2, improving user experience and accessibility
- Increase Ecosystem Yield: Leverage the higher yield of stMATIC to enhance overall ecosystem returns

## Proposed Solution
We propose to integrate stMATIC into the Morpheus ecosystem, allowing stMATIC holders to become capital contributors. This will be achieved through smart contract modifications and dashboard updates to support Polygon L2. Our solution leverages cross-chain technologies like Wormhole and LayerZero for seamless MOR token functionality across chains, enhancing the Morpheus ecosystem's chain-agnostic vision and supporting decentralized AI ("DeAI") applications through enhanced privacy and efficiency provided by zk-rollups.

## Technology Stack
- Blockchains: Ethereum, Arbitrum, Polygon
- Cross-Chain Protocols: Wormhole, LayerZero
- Smart Contracts: Solidity for Ethereum and Polygon adaptations
- Frontend: React.js for dashboard updates, with Web3.js and Ethers.js for blockchain interactions
- Security: Comprehensive testing and auditing using tools like MythX and OpenZeppelin
- Diversification of Protocol-Owned Liquidity

To enhance the diversification of protocol-owned liquidity and support deeper liquidity across multiple ecosystems and pools, the yield generated from assets will remain within the ecosystems where they were generated. For example, yield from stMATIC will not be converted to ETH on Arbitrum but will stay in a liquidity pool of stMATIC/ETH on Polygon. This approach prevents the concentration of liquidity, ensuring that ecosystems outside of Arbitrum are not limited to user-provided liquidity alone.

## Bridge MOR to Polygon Using the Native Polygon-Ethereum Bridge

MOR tokens will be bridged to Polygon using the native Polygon-Ethereum bridge. This enables MOR to participate in the Polygon ecosystem while maintaining its primary operations and functionalities on Arbitrum. 

Despite MOR being accessible on multiple chains through bridging, all MOR tokens will remain claimable only on Arbitrum. This decision is to avoid the complexity and potential confusion arising from having MOR balances claimable across different blockchains.

## Calculation of MOR Emissions to Capital Contributors

The calculation of MOR emissions for capital contributors, when involving more than one asset, will adopt the Pro Rata (Yield) method. This approach considers the yield generated by each asset, ensuring emissions are aligned with the financial benefit provided to the Morpheus ecosystem. For instance, if stMATIC yields 4.3% on $100M, and stETH yields 3.6% on $400M, MOR emissions will be distributed 23% to stMATIC depositors and 77% to stETH depositors. This method is deemed the fairest, aligning emissions with the actual financial contribution of each asset to the ecosystem.

Deposited Asset 
Deposited TVL
Yield %
Annual Yield
% of Yield = MOR Emissions
stETH
$400,000,000
3.6%
$14,400,000
77%
stMATIC
$100,000,000
4.3%
$4,300,000
23%
Total
$500,000,000
n/a
$18,700,000
100%

## Impact on Community Emissions

The adoption of the Pro Rata (Yield) method for calculating MOR emissions to capital contributors will also influence the distribution of Community Emissions. Currently, 1/3 of Community Emissions, which constitute 8% of total emissions, are designated for front-ends that facilitate capital contributions. For consistency, this proposal would require Community Emissions to also be calculated based on Yield generation rather than Capital inflow. 

### Implementation Plan
Project Initiation and Community Feedback
Expand the initial community feedback phase to specifically gather insights and opinions on the new liquidity management approach and the Pro Rata (Yield) method for MOR emissions. This will ensure broader community support and understanding of these strategic decisions.

### Detailed Project Planning
Include detailed planning around the implementation of yield-based liquidity pools, particularly the setup and management of stMATIC/ETH liquidity pools on Polygon. This should cover technical, operational, and governance considerations.
Plan for the integration and testing of the bridge for MOR token to Polygon using the native Polygon-Ethereum bridge, ensuring seamless token transfer while keeping the claim process confined to Arbitrum.

### Smart Contract Development for stMATIC Integration
Develop smart contracts not just for stMATIC contributions but also for managing the protocol-owned liquidity in a way that keeps yield within its original ecosystem. This includes creating and managing liquidity pools on Polygon.
Incorporate logic to calculate MOR emissions based on the Pro Rata (Yield) method, ensuring fairness and alignment with the ecosystem's financial contributions.

### Cross-Chain Functionality Implementation
Emphasize the development and testing of cross-chain functionality that supports the unique approach to liquidity and emissions calculations. This includes ensuring that the bridging of MOR to Polygon is seamless and that the claim process remains straightforward on Arbitrum.

### Dashboard Updates and User Experience Enhancement
Update the project plan to include dashboard enhancements that accurately reflect the new liquidity management strategy and the emissions calculation method. This includes clear visualization and reporting for users on how yields are being generated and how MOR emissions are calculated and distributed.

### Cross-Chain Integration Testing and Security Auditing
Ensure testing protocols include scenarios specific to the decentralized liquidity management strategy and the Pro Rata (Yield) calculation for MOR emissions. This will help identify any potential issues in how these strategies are implemented across different chains.
Security auditing should also focus on the new aspects introduced by these strategies, particularly the smart contract logic handling the yield-based liquidity pools and MOR emissions calculations.

### Project Completion and Ecosystem Integration
The completion phase should include a review of how well the project has implemented the strategy for decentralized liquidity management and the Pro Rata (Yield) method for emissions. This includes assessing the impact on the ecosystem's liquidity depth across multiple ecosystems and pools, as well as the fairness and transparency of MOR emissions to capital contributors.
