
![DAI-ecosystem](https://github.com/DecentralizeAI/MRC/assets/76454555/d4be1474-3046-4fc3-8803-a880038b78aa)

# Building Decentralized AI

On December 9, 2023 the Decentralized AI community assembled from around the world at Kiretsu in Austin, Texas in order to begin contributing to this repository.

The objectives are to define
    1. The tech stack
    2. Practical technical standards for collaboration within in the community

Morpheus encourages and will incentivize developers who propose or implement new standards/integrations between open source projects in DeAI.

Live Journal

## Morpheus - David A. Johnston

Morpheus is designed to incentivize the first peer-to-peer network of personal AIs, known as Smart Agents. Providing users open-source Smart Agents to connect to their wallets, Dapps, & smart contracts promises to open the world of Web3 to everyone.

<https://twitter.com/DJohnstonEC>

**Key points:**

- 230 days left until July 26, 2024 - the date the commerce department is mandated to deterine if open source wieghts conssttiute munitions
- EO signed on October 31st
- Limits number of parameters models can have
        - limit for permissionless models at 10B parametrs and only 20gigs
         - KYC for data centers
- Only an 8 month timeline to build open source tech stack

- permissionless building is the heart of what we’re trying to do

- Phil Zimmerman is the patron saint of decentralized AI
        - In 1991, a bill was introduced to ban encryption for email, so Phil introduced PGP, because privacy is a human right
        - He printed his work on a t shirt and was arrested for disclosing the RSA algorithm.
        - Won in supreme court based on free speech grounds, who recognized that code and speech were protected
- This is why your email can legally be have private
- A few weeks ago in SF the Keep AI Open event was announced and within 48 hours >700 people showed up at the end of OpenAI's dev day
- Marc Andreessen is constantly posting memes for decentralized AI
  - the right tot bear compute
  - come and take it
- Balaji Tweet:
    "free internet means free AI
    we will fight government control over compute with everything we have"
- Morpheus is decentralized open source AI, and the tech stack for decentralized AI
  - anonymous group dropped paper in September
  - within 45 days community had built implementation
  - live now can run on computer locally
  - fully open source LLM running on your data
  - MOR smart contracts entering testnet today
- We want this to continue beyond today
  - join discord
  - channel for every project os people can follow up with questions
  - engage with everyone building models, fine tuning, agents, every part of tech stack
- The goal is 1 billion users for decentralized AI
  - AI is the opportunity to get a billion people into crypto by removing technical barriers to access web3
  - With AI, we build off the expressed intent,
  - On Morpheus, it knows what smart contracts are available
- The AI community: needs censorship resistant compute and tools to monetize agents

## Anna Zazlauskas - Vana

Vana: Own your data

***Key points***

- data ownership
- goal: world where users own data and value it creates
- initial belief: token incentives enable large scale RLHF and data labelling
  - people who want to sell data do so out of desperation
  - not the best dataset
  - uphill fraud battle
  - people constantly finding ways to sell bad data
  - people who want to sell data for financial reward are not representative
  - mostly doing out of financial desperation
  - users choose products that align with ideologies, value privacy and agency
- Reality:
  - users choose whatever is most convenient or capable. privacy/security are afterthoughts.
  - slacktivism

- initial belief: data ownership legislation like GDPR and CCP will help.
  - regulation favors consumers.
- learning: even if users have a legal right ot data, it is inconvenient to access. users have to be very motivated.
  - regulation favors incumbent.

- you can ask for your labels on instagram

- On Vana:
  - make a personal data tangible through a personalized ai model
  - bring your model with you throughout internet
  - users host their own nodes or opt for a convenient hosted option
  - private data stays on user's node, while third party apps run inference.
  - granular permissions so you can let people access your data or models.

- Modalities:
  - image: train lora based on 10 photos of yourself
  - text: personality + memory stream from your social data and messages
  - audio( hosted) based on 1min of your voice
  - best audio models are closed source (?)

- memory architecture
  - query memories based on relevance, important, and recency
  - summarize relevant memories to fit in context window
  - for more, read Generative Agents: Interactive Simulacra of Human Behavior

- bootstrapped network by building viral consumer applications in house
  - 1.2M users
  - 700k private models trained
  - 10M personal data points

- collective models
  - users contribute data to models they collectively own and govern
  - users decide who can access the model, how much to charge, how it can be used
  - each collective has its own node, similar to a user’s node

- host your own vana node
  - connect your social data, journal entries, messages, other personal data with an ally that deeply understand you
  - everything stays on yoru machine
  - can open up an endpoint to use it throughout apps
  - reach out to <anna@vana.com> to try this out

## Ritual - Niraj

Integrate AI models into your protocol, application or smart contract with a few lines of code.

Described a global statistical computer.

__Key Points:__
- motivation:
    - ai is eating the world
    - usage going up massively
    - decentralized intelligence improving

*problems of AI today:*
- infrastructure highly centralized
    - model storage
    - model governance and ownership (e.g. OAI fiasco)
    - model compute (training, inference, fine tuning, etc)
    - access to training data
- ai infra is highly permissioned
    - high costs ot using/improving AI
    - permissioned centralized APIs to access
    - no privacy/computational integrity censorship resistance
    - most OSS models are highly red-teamed/censored
    - many geographical limitations
- AI infra is increasingly regulated
    - ai incumbents and governments attempting strong regulatory capture
    - “we know what’s in your best interests”

- future impact
    - as AI gets inserted into every tech product, new forms of censorship/manipulation ill take place
    - LLMs and other foundation models create highly engaging forms of propaganda (e.g. 2024 US election media)
    - political ideology weaponized by who controls distribution and access to models
    - open and transparent governance of AI models is key
    - “who controls models controls the world”

*AI x Crypto to the rescue*
- AI is highly centralizing tech
- crypto is highly decentralizing tech
- combining both solves aforementioned problems
- trustlessness + intelligence = ???won’t be evil -> can’t b evil
- if we’ve decentralized money, music, property records, etc, why not AI?

At Ritual:
- how do we get AI into hands of crypto devs today
- combine best of ai and crypto to make it easy for devs to build crypto x ai products
- model specific computational integrity (opML and zkmlO
- privacy (FHE for classical ML models, MPC for foundation models)
- ritual AI VM with stateful precompiles for various model operations (inference, FT, quantization, embeddings)
- supports Ethereum base chain and rollups, alt L1 support coming in 2024

- tech pillars
    - censorship resistance and decentralization
    - privacy
    - computational integrity
    - incentives

- infernet: network for inference
    - take smart contract, plug into model
    - allows you to customize infra
    - set up nodes yourself, run inference for your products

- frenrug
    - on-chain smart agent that buys and sells friend.tech keys if you can convince it
    - built on internet SDKs
    - internet llm nodes generate responses, feeds into on-chain classifier (with ezkl proof)github.com/frenrug/contracts
    - frenrug.com

<https://twitter.com/niraj><br><https://ritual.net><br><https://x.com/niraj><br><niraj@ritual.net>

## Akash Network - Greg Osuri

Akash is open-source Supercloud that lets users buy and sell computing resources securely and efficiently. Purpose-built for public utility.

Greg's demo showcased the options available on the network and the ability to spin up new services.

<https://akash.network>
<https://twitter.com/gregosuri>

## Agora Labs

### Anish

Cloud-agnostic MLOps/LLMOps platform powered by cheap, decentralized compute.

<https://twitter.com/agora_io>

## Bittensor

### Carro & Const

Bittensor's vision for a decentralized AI company has captivated a large number of people in the arenas of Artificial Intelligence and computer science, who have yearned for an alternative to the top-down world being created by our current technology giants. However the promise of what Bittensor is and can be has been masked by large technical barriers to understanding, and thus has not been well digested by non-technical audiences.

<https://twitter.com/0xcarro><br><https://bittensor.com/docs>

## FreedomGPT

### John Arrow

FreedomGPT 2.0 is a launchpad for AI with an “App Store” where no technical knowledge is required to use the latest AI models.

<https://twitter.com/JohnDavidArrow>

## EdgeLLama

### Varun Mathur

EdgeLLama, and the associated set of products, which lead to a seamless AI consumer-cloud will impose a similar abundant forcing function on AI as well. You can go ahead and cancel your $20/month Pro plans, because this next wave of AI, runs in your laptops, desktops and smartphones, and is good enough.

<https://twitter.com/varun_mathur><br><https://hyperspace.computer/><br>

## Nous Research

Nous Research is a private applied research group. We publish open-source work in the LLM domain, including local models, datasets, and core architectural improvements.

The demo included a walkthrough of the Nous software.  It showed the ability to build AI via drag and drop.  Am explanation of their research described YaRN, Hermes, Obsidian, and Capybara.

<https://nousresearch.com/><br><https://huggingface.co/NousResearch><br><https://discord.gg/jqVphNsB4H>

## io.net

### Angela Yi

io.net is a state-of-the-art decentralized computing network that allows machine learning engineers to access distributed Cloud clusters at a small fraction of the cost of comparable centralized services.

io.net deploys GPU clusters from multiple locations that are not constrained by colocated devices. The platform supports clusters of any scale, allowing engineers to deploy a 20K GPU cluster within seconds.

io.net has 3 key elements:
    1. IO Cloud, where engineers can seamlessly deploy their GPU clusters.
    2. IO Workers, where suppliers can connect their devices, monitor their performance, and keep track of their earnings and rewards.
    3. IO Explorer, where we provide transparent, real-time information on pricing, as well as devices and clusters, and inferences powered through our network.

<https://io.net/>
<https://discord.gg/65y7Kma4>
<https://t.me/ionet_official>

## Commune AI

Commune is a protocol that aims to connect all developer tools into one network, fostering a more shareable, reusable, and open economy. It follows an inclusive design philosophy that is based on being maximally unopinionated. This means that developers can leverage Commune as a versatile set of tools alongside their existing projects and have the freedom to incorporate additional tools that they find valuable.

<https://twitter.com/communeaidotorg>

## Actioneer

### David Orban

Dignity and purpose for 8 billion humans in an age of AI

<https://twitter.com/davidorban>
<https://github.com/actioneerai>

## OpenCog Hyperon

The open-source software framework bringing together multiple AI paradigms in a cognitive architecture oriented toward AGI at the human level and beyond

<https://twitter.com/OpenCog>
<https://github.com/opencog>

## Hypercycle

HyperCycle is building a tiny but essential component that enables AI Machines to transact with other AI machines in a sub-second finality which results in unprecedented emergence.

<https://twitter.com/hypercycle_ai>

## The Lifted Initiative

### Eric Bravick

The Lifted Initiative is building a comprehensive web3 native cloud with a focus on easy to use tooling.  We've launched about 17 product and service groups to date into private Beta, including support of AI use cases.  We go public in 2024 and we are currently seeking integrations with other AI focused networks.  We believe strongly in decentralization of networks (multi-network approaches) and will be embracing a wide array of partnerships rather than a "build it all on one chain" philosophy.

<https://twitter.com/ebravick>


