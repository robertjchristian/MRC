
## Morpheus MRC-24: Smart Agent Product Strategy


---
This MRC24 has a lot of great points for developers to reference when they build their agents.

IN PROGRESS

---


### Purpose

Existing work has focused largely on the Morpheus node, funding mechanisms and tokenomics. Many developers joining the project are seeking guidance on building Smart Agents. This MRC sets out a roadmap for Smart Agent development, starting off by analyzing end-user needs, identifying common agent capabilities, opportunities for trust minimization and ultimately proposing a technical strategy for a Smart Agent SDK.

A variety of use cases are explored in order that the community can begin to build some consensus around priorities.  We then map out common architecture and data requirements without being prescriptive of implementation details.


* Extends [MRC-0 Smart Agent Protocol](https://github.com/SmartAgentProtocol/SmartAgents/blob/main/White%20Paper.md) paper.
* Provides concrete examples of user needs for Smart Agent developers
* Defines common agent capabilities
* Defines common data requirements
* Provides UX examples
* Provides Architecture recommendations and high-level technical strategy


### User Needs

Too many decentralized projects fail because they assume that the average user also cares about decentralization. Wrong! The average user doesn’t care and will choose the product that provides them with the best feature set and UX. We must accept this and ensure that we have a strong product focus in order to succeed and be sustainable in the long term.

One of the founding visions for the Morpheus project is to become a decentralized ChatGPT. In order to realize this goal, the project should initially focus on the smaller domain of crypto users. Focusing on a smaller domain will increase the probability of finding traction with early users. Real traction will only be achieved by offering superior performance when compared to more generalized and easily available offerings such as ChatGPT.

The first step along this path is to understand the needs of crypto users, and how Smart Agents can help them. Of course there are many different types of users with a diverse set of needs, so we start by defining several different user personas.


#### Personas

* **Noob** - just getting onboarded and dealing with common issues.
* **Investor** - makes long-term investments in tokens and dabbles with DeFi.
* **Degen** - needs access to a wide variety of information to perform complex analysis.


#### Epic User Stories

Let’s now define some user stories for each persona to help flesh out the design space.  


##### Persona = Noob

* I want to learn about concepts such as wallets, gas, transactions and how to stay safe.
* I want to learn about and compare available products such as DEXs, money markets.
* I want to understand and compare the various options that are available in the market for categories such as wallets, chains, DeFi protocols.
* I want to be made aware of the risks of available products such as exchanges, DeFi protocols.
* I want customer support on basic issues such as dealing with stuck transactions.
* I want to know what these tokens are that are in my wallet.


##### Persona = Investor



* I want to research projects to invest in, this may involve asking questions about their technology, tokenomics, team, community, traction (users / TVL etc.), price history, token holders and more.
* I want to be able to compare projects based on these dimensions and my preferences.
* I want to be made aware of important changes to projects that I’m invested in.
* I want to keep up with important decisions that are being made in the DAOs / communities that I’m a member of.
* I want to know about important events that are happening related to projects that I’m invested in, e.g. mainnet launch, conferences.
* I want to be made aware of airdrops that I’m eligible for based on the tokens that I’m holding.
* I want to be made aware of and participate in important governance decisions.
* I want to do basic analysis of simple HTF investment strategies, e.g.  what is the average return, drawdown, Sharpe ratio of a strategy that buys bitcoin 1 month before halving and sells it 18 months later.


##### Persona = Degen



* I want to generate trading signals from real-time news events  - e.g. Uniswap governance proposal to turn on fee switch.
* I want to find airdrop farming opportunities, this may involve strategies such as finding projects that haven’t launched a token yet but have a product. I may want to know about their number of users, TVL, volume, fees and other metrics to calculate the EV.
* I want to simulate strategies that may involve complex DeFi protocols.
* I want to be able to track a large number of tokens and be alerted when certain criteria match.
* I want to track wallets and be alerted when they make transactions that match a certain criteria.  
* I want to execute orders across multiple venues, considering factors such as liquidity, price impact, capital efficiency.
* I want to manage multiple strategies across multiple wallets, this involves performance tracking, risk management (e.g. liquidation when using money markets, perps).
* I want quick answers to questions like “what is the 30d average yield on the ETH/USDC 3bps Uniswap pool”.
* I want to watch whale wallets or newly funded wallets that make large purchases.
* I want to perform qual / quant research such as: What were the first Ordinals projects, sort them by sharpe ratio of their returns since launch.
* I want to be notified when certain conditions are met for any of my open positions, e.g. daily volume > market cap.
* I want to calculate a relative valuation for a new token, this may include finding comparables, and building a suitable model based on assumptions and relative metrics.


### Product Vision - Example User Experience

Let’s elaborate one of the more complex user stories.  For now we’ll just imagine the end user experience before we then work back to the Smart Agent capabilities, data requirements and architecture.

**User story:**

I want to generate trading signals from real-time news events  - e.g. Uniswap governance proposal to turn on fee switch.

**Step 1:**

Degen receives an alert from one of their agent subscriptions - GovAgent. This agent is responsible for ingesting all governance proposals and classifying them as to whether they are likely to have an impact on the token price of the project.





![alt_text](https://mor-assets.s3.amazonaws.com/feed.png "image_tooltip")


**Step 2:**

The user sees the alert and clicks on it to start a new chat, inviting GovAgent to participate.  GovAgent provides further analysis of the governance proposal, and suggests possible impacts, such as a rerating of revenue-generating DeFi protocols that do not currently distribute revenue to their users. The user decides to pursue this and requests an analysis of undervalued DeFi tokens, which our local agent delegates to the Data Analysis tool.

The Data Analysis tool has the ability to split the goal into multiple tasks with its own agentic planning and reasoning process. It plans and executes steps to get the necessary data (considering our previous preferences for data sources), calculate the new variable we requested and display a table of results.

The user inspects the table and decides they want to purchase MKR token, triggering a transaction to be confirmed in the user’s wallet.





![alt_text](https://mor-assets.s3.amazonaws.com/uniswap+chat.png "image_tooltip")



### Agent Capabilities

Without prescribing any particular agent architecture, we can extract from the above user needs a set of capabilities that agents may have.


#### Crypto Knowledge Integration

In order to be able to interpret most of the above user stories it is necessary for agents to have a thorough understanding of relevant concepts. There are two main technical strategies available to achieve this with LLMs:

**1: Fine-tuning a foundation model**

Fine-tuning refers to a transfer learning technique where we take a pre-trained foundation model and update its parameters by further training on a domain-specific dataset. This process aims to integrate knowledge of the new domain in the general-purpose foundation model.  The main issue with this approach is that it is expensive and very sensitive to the data and parameters used for training, so it cannot be repeated frequently to update the model with anything like real-time data.

Note that it’s currently inefficient to train large models in a trustless distributed computing paradigm, so there is a degree of trust involved regarding the training data and process. However, this is also the case for the foundation models we rely upon.

An example use case that would be addressed by fine tuning would be the n00b’s need to “_learn about concepts such as wallets, gas, transactions, and how to keep myself safe_.”

**2: RAG - Retrieval Augmented Generation**

RAG refers to a process where we integrate information retrieval into the response pipeline.  An agent may initially interpret a user prompt, identify that external data is required in order to proceed, call a tool to look up the data and then inject that back into the context so that the model can integrate up-to-date information in its inference process.

There are a number of security concerns when it comes to the retriever system which we will discuss further in the “data requirements” section. Suffice to say that there are strong financial incentives to manipulate data within our domain.

An example use case that would be well addressed by RAG would be to “research a new novel DeFi protocol by asking questions about its docs and whitepaper”.


#### Data Retrieval

In order to implement RAG or data analysis systems, it is necessary to retrieve reliable and accurate source data. Data is the life blood of the system and its importance cannot be overstated.

The necessary source data may exist on-chain in some cases, but in the vast majority of cases the data is held in unstructured or semi-structured form on centralized servers accessible only through third party APIs.

By inspecting the user stories outlined above we can see that there are many common data source requirements, these include: [current example sources in square brackets]



* **Code** (after all, it is law) - [Github, Etherscan]
* **Project documentation** - [Whitepapers, Docs]
* **Blockchain raw / enriched data**- [RPC nodes, Graph Protocol]
* **Blockchain analytics & labeled wallets** - [Nansen, Arkham, Messari]
* **On-chain price oracles** - [Chainlink / Pyth]
* **Aggregated price / volume / coin metadata** - [Coingecko]
* **Social media** - [Discord, Twitter]
* **SocialFi** - [Farcaster, Lens]
* **News articles and podcasts**

While some data such as “current price” can be pulled quickly from reliable sources such as oracles, much of the data we require necessitates a lot of preprocessing before it can actually be used.  A typical data pipeline would involve:



* **Curation** - where we decide which data sources to trust, or how to weight multiple sources.
* **Collection** - a process that ingests the data regularly into some sort of a data warehouse and deals with any errors in that process.
* **Pre-processing** - any transformations or aggregations that are necessary
* **Indexing** - storing the data in a format that makes it fast to query for our purposes

Some data may be only available behind a paywall, opening up the question of how this cost is structured between agent developer and end user, and also the question of payment rails in the case that the data source is off-chain.

In some cases there are decentralized indexes available with on-chain payment rails; for example the Graph Protocol indexes transactions and events from a number of blockchains in subgraphs. In many other cases however the only way to access indexed data is through a centralized API or by building your own index.

We could just leave this as an implementation detail for each agent developer but in this case we would miss out on most of the benefits of decentralization. For example, we would have no guarantees about the integrity or provenance of the source data that the agent is using or how it is being processed. There would also be duplication of effort of each agent developer having to manage their own data ingestion, storage, model training, search and RAG systems.

Misinformation is rife and there are strong incentives for agents and data providers to manipulate data when there are financial benefits for doing so.  For this reason we strongly suggest that the Morpheus project considers building a shared source of truth in the form of a decentralized data lake. While the implementation details are outside of the scope of this document the following points should be considered:



* **Performance** - The speed and efficiency with which data can be retrieved, processed, and analyzed are paramount. High performance is essential for real-time analysis and decision-making processes.
* **Availability** - Ensuring that data is consistently accessible is crucial for reliability and verifiability. Protocols such as Filecoin’s Proof of Spacetime (PoSt) can verify that data is stored correctly and securely over time
* **Verifiability** - It should be possible to verify the provenance of the data and have full transparency in the processing that has taken place along the pipeline.
* **Incentives** - There should be some mechanism in place that incentivizes honest curation, collection and processing of the data. Ocean Protocol has done some work in this area.

Due to the scale of this problem we expect it to be initially out of scope for the core Morpheus project, but we do need to define best practices for agent developers and data providers to address these concerns and ensure that users are aware of the risks regarding data.


#### Blockchain Analysis

Blockchain analysis encompasses the examination and interpretation of blockchain data to extract meaningful information regarding transactions, events etc.

Consider the user query: “What is my cost basis for token X”?

Our approach could be to index all the user’s historical transactions, identify those that changed our balance of token X, assume that they are swaps and get the price of the input tokens at the time of the transaction.  However, reality is much more complex, e.g. what if we received these tokens as a result of staking another token, or as LP rewards.

Again this is an area where many centralized services are available to call upon in the first instance who have done the heavy lifting of indexing user transactions, classifying transactions and events such as depositing into an LP.


#### Contract Understanding

Contract understanding involves the ability of agents to read, interpret, and analyze smart contract code. This is crucial for assessing the functionality, security, and potential vulnerabilities of DeFi protocols and other blockchain-based applications.

It is likely that the agent would call a tool that contains a specialized model for this task. One approach is to fine tune a code-specialized mode (e.g. CodeLlamal on suitable training data, for example solidity code and its documentation, or audit reports.

Consider the query: “What are my unclaimed rewards from &lt;yield_farm_X>”

Assuming that &lt;yield_farm_x> just popped up last week and hasn’t provided Morpheus with a nice tool or agent to call to retrieve this information, our agent might be able to find the relevant contract, realize that it’s a Uniswap v2 clone, and therefore know which function to call to answer the question.


#### Code Generation, Execution, and Debugging

Many use cases involve computation of numerical data, LLMs themselves are not good at this but fortunately computers are good at it. Computers run code and LLMs can write code.

Consider the query: “What is the sharpe of a strategy that buys bitcoin every time weekly price closes above 100 day MA and sells when price closes below”.

Our “data retrieval” component would be charged with the task of getting the data but then we need to write some code to perform the backtest.

There are several code generation models available (e.g. [codellama](https://huggingface.co/docs/transformers/model_doc/code_llama)) that could be used as a foundation for fine-tuning with crypto and financial domain knowledge.  There are also models that generate SQL which may be used for querying sources such as the [BigQuery Ethereum public dataset.](https://cloud.google.com/blog/products/data-analytics/ethereum-bigquery-public-dataset-smart-contract-analytics)

Code generation is just the first step in an agentic process that must also be able to execute and debug the code.  There are obvious security concerns with arbitrary code execution and proper sandboxing is essential.


#### News Impact Analysis

Consider the product vision example where an agent is finding trade opportunities by assessing the impact of governance proposals.  There are also many other cases where it’s necessary to assess the impact of new information on our investments that require a similar capability.

Speed and throughput are important in this case and therefore it’s likely that specialized “classifier” models may be employed for the task of assessing relevance in the first instance due to the large context window required.


#### Agentic behavior

While many interactions may be simple one-shot questions and answers, the real magic of agents comes from their ability to break down goals into subtasks, use tools and reasoning methods such as chain-of-thoughts, tree-of-thoughts, graph-of-thoughts.

Several open source frameworks are available to manage the orchestration of these processes, including langchain, autoGPT and CrewAI.


#### Execution / Transaction Construction

The most simple and reliable initial implementation would require transaction construction to be hardcoded for a number of whitelisted protocols.  E.g. a “swap” tool may support the most popular dex aggregator on each chain - currently 1inch for EVM, jup.ag for Solana etc.

A more advanced approach that enables interaction with arbitrary contracts would be to extend the contract understanding capability to be able to also generate transactions that interact with the contract.

It is recommended that the Morpheus project does not concern itself with optimizing execution strategies since this capability is likely to be provided by upcoming intent / solver based protocols.


### Smart Agent SDK Architecture [WIP]

The [Smart Agent Protocol White Paper](https://github.com/SmartAgentProtocol/SmartAgents/blob/main/White%20Paper.md) provides a high-level overview of the function and incentive mechanism for Smart Agents, and the [Smart Agent repo](https://github.com/MorpheusAIs/SmartAgents) contains an initial agent implementation. We extend this work and propose the development of a Smart Agent SDK that will create a flexible foundation for agent developers to build upon, addressing a number of common needs without prescribing any specific agent implementation, framework, or models.  This may be delivered as a v2 of the existing Smart Agent project.



![alt_text](https://mor-assets.s3.amazonaws.com/smartagentarch.png "image_tooltip")


The diagram shows the key components that the Smart Agent SDK is concerned with. It is initially expected to run entirely locally but may be **progressively decentralized from the bottom-up.**  I.e. first storage and compute, then models (inference) and indexes as these services become available.

A Smart Agent may run entirely stand-alone, or it may register itself with the Morpheus network, in which case it can coordinate with other agents and offer its services to the network.  

It should be **agent orchestration framework agnostic**, but provide adapters for common frameworks such as langchain, AutoGPT, Crew AI so that agent developers can use their favorite framework.  The SDK will also provide a light wrapper for tools, making them easily reusable by other Smart Agent developers.


#### Registration and discovery

Agents should provide a manifest that contains all the details a user needs in order to assess whether it is suitable for their needs.

Best practices should be developed for disclosing any data sources or potential quality issues as these propagate downstream. This disclosure process also enables auditability - independent auditors can assess whether the agent does what it says it does.

Agents may register themselves with a central smart contract (see proposed work by [Lumerin](https://lumerin.io)).  There should be a decentralized reputation system overlaid on this to help users decide which agents to trust.  This smart contract will act as the registry for an agent marketplace.

See: [MRC 10: Development of Smart Agent Tools Marketplace](https://docs.google.com/document/d/1JJQR4-b63VbJQ_etSt5Poyk1KcK3f7FvUZcwKB5Zpk8/edit).


#### Tool Use (and re-use)

The SDK should aim to encourage tool code reuse by enabling compatibility of tools between competing agent frameworks, and providing an open source repo to share tools.

The interface for a tool can be very light, including at at minimum:



* Purpose of the tool
* Input format
* Output format

An example of a tool may be a “contract understanding” tool, that is fed a contract address and a natural language query. Tools can be simple or complex, they may specify that certain models are downloaded, or even call out to external services.


#### Multi-Agent Collaboration

See: [MRC 11: Morpheus Multi-Agent Framework](https://docs.google.com/document/d/1i6FBD7OIMEHSYMgKUGmrjpxgnlFN20JRC4_yW9bAVWw/edit).

[Should this be a tool or first class component of the framework?]

[Requires a peer-to-peer communication protocol.]


#### Incentive / payment mechanism

Coordinate with Lumerin on payment model.  Consider:



* Different service types - consider query-based, service based (one-off or recurring - e.g. alerting), time based - e.g. 1d of usage.
* Agent developers may need to pay external data costs, e.g GRT tokens for graph queries.
* Consider also agent-agent transactions


#### UI

A simple UI should be provided for agent developers that includes:



* Chat window.
* Wallet connection.
* Useful components such as price charts, and other formatters.
* Tracking for jobs running
* Agent subscriptions, payments etc.


#### Risk Management

There should be a global risk management module that is maintained by an independent Morpheus security group rather than individual agent developers. This should act similarly to a virus scanner or “rug detector” in an adversarial manner, inspecting any proposed transactions before they trigger the user’s wallet.  The Smart Agent framework should provide an interface that acts as a proxy for web3.js or similar.

The SmartContractRank algorithm is the first implementation of this functionality.

This module may also implement cost controls and other user configurable guardrails.


#### Evals

Developers who make their agents or tools available either as open source or as a Morpheus service should consider how to evaluate whether their agent is performing well. These evals should be open for verification.


### Next Steps



* Get community feedback on this document, aiming to validate the user needs and refine the technical strategy.
* Engage with interested developers to define and prioritize tasks.
* Build out the Smart Agent framework / SDK, either as a new repo or as an update to the current [Smart Agents repo](https://github.com/MorpheusAIs/SmartAgents)

