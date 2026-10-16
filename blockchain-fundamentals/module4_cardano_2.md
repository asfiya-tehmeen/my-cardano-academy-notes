Scalability is a blockchain’s ability to handle usage or adoption. Measuring scalability is not simply measuring the TPS (transactions per second), it is more nuanced than that. TPS is perhaps the crudest metric to use as transactions occur in a variety of sizes and formats. Instead, we must consider a wide range of metrics:

- Throughput is the quantity of data that a system can process in a given length of time.
- Script execution time, how long was the CPU busy for?
- Finality is the amount of time it takes for a transaction to become immutable
- Concurrency is the amount of work various actors can do without interfering with one another.
- The actual size of transaction(s)

Any blockchain can appear fast using tiny transaction sizes and no scripts. Some high profile blockchains have centralized characteristics such as a minority of validators controlling disproportionate amounts of stake. It’s easy for a blockchain to compromise on decentralization then boast astronomical TPS figures.

We should also note that throughput means something different in a UTXO system than it does in an account-based system. TPS on Cardano is yet more nuanced due to its native asset capability. eUTXO allows hundreds, even thousands, of native assets to be transferred in a single transaction. Nearly everything on Cardano occurs as a transaction, and generally speaking resources are consumed from these types of activities…transferring ada, issuing assets, executing smart contracts, voting and adding metadata. A more accurate metric is therefore TPT (transactions per transaction). To understand and visualize how transactions work on Cardano, visit eUTtxO.org, a blockchain explorer which presents a live view of blocks, and their contents, being created.

There is no ‘magic bullet’ for scaling blockchains, it’s done by tweaking parameters and combining different solutions that generally fall into two categories:

- Layer 1 solutions: upgrades applied to the mainchain, ie. Cardano.
- Layer 2 solutions: offloading workloads, extending functionality and integrating other blockchains with sidechains, ZK rollups and state channels.

Scaling solutions are usually categorized as either On-chain solutions which encompass block size increases, pipelining, input endorsers, parameter adjustments, Plutus script enhancements, node enhancements and on-disk storage improvements. Then there are Off-chain solutions including sidechains, partner chains, Hydra, off-chain computing and Mithril. We’ll dive deeper into these solutions in future courses.

There's also the actual size of the blockchain to take into account. Blockchains can store data infinitely. All transactions recorded on the blockchain are logged regardless of relevance as the number of transactions per second increases. A bloated blockchain leads to slower sync times for wallets, it’s like flooding your basement with water. It’s likely to make life difficult in the long term. Cardano’s architecture focuses on moving a lot of the computation off chain and storing the minimum on the mainchain. Bitcoin’s blockchain size passed half a terabyte in late 2023, Ethereum, on the other hand, requires wallets to download over a terabyte of data to sync. Cardano compares favorably at 177 GB if you consider Solana has bloated to 3.8 terabytes.

We talked about the Lightning Network on Bitcoin earlier. Hydra is another Layer 2 scaling solution tailored for Cardano.

Hydra introduces isomorphic state channels to increase throughput with reduced transaction fees and storage needs. Hydra is developed using principled, evidence-based research making it easier to perform transactions off-chain while utilizing the main-chain ledger for secure settlement.

Hydra can sound very complicated but lets demystify some of the jargon. Let’s first clarify what ‘isomorphic state channels’ are. ‘Iso’ is a prefix meaning equal, like you may have heard the term isometric, meaning equal measurements. ‘Morphic’ is related to shape or form. So isomorphic means having the same structure and properties.

‘State channels’ extend the idea of payment channels to also support smart-contracts over off-chain channels. Participants in the channel can now, in addition to traditional transactional payments, execute scripts to handle complex logic, off-chain, before committing the result back to the layer 1 mainchain.

Participants lock funds into a smart contract. They can then transact with others in the state channel, off-chain, in whatever fashion meets their use case. Afterwards, the outcome is settled on-chain, without requiring the full transaction history of what occurred off-chain in the meantime.

Developers can leverage Cardano’s proven infrastructure to develop wallets and dApps that communicate with the layer 2 system, drastically reducing the learning curve for Hydra.

While Hydra is being developed in collaboration with the Ouroboros protocol and the Cardano ledger, it may also be used with other systems that have the same properties as Cardano. Hydra replicates the main chain’s functionality while minimizing friction for users, but still allows the flexibility of having a different fee structure and timing constraints on the layer 2.

Hydra gels seamlessly with Cardano as extended UTXO and smart contracts allow developers to build rich isomorphic state channels. In comparison, the Lightning Network faces some friction as Bitcoin does not support programmability.


You may often hear the term tokenomics in regards to cryptocurrencies. This is referring to the economic model of a coin or token, including its total supply, circulating supply and initial distribution among other factors. Cardano had a very fair token distribution, in comparison to its counterparts with 80% of ada owned by the public.

The total supply of 45 billion Ada refers to the amount of ada that will only ever exist and approximately 35 billion of that is the current circulating supply. Cardano's monetary policy is a carefully considered approach to ensure the inflation rate remains low in the long term. This is achieved by setting a parameter to control the maximum percentage of ada that can be released in a given period. The Cardano monetary policy is the result of academic research on the game theory associated with inflation, including a rigorous analysis of the effects of Cardano's circulating supply on its overall value.

Cardano's monetary policy is designed to incentivize stake pool operators to participate in the staking model to guarantee the long-term sustainability of the network. Ada holders who delegate and stake pool operators are rewarded for their support with a proportion of ada each epoch, in addition to transaction fees.

Transaction fees are deterministic, or predictable, for developers interacting with Cardano. Compared to other cryptocurrencies, Cardano handles fees a little differently. Fees do not go straight to the block producer. Instead, they are pooled and distributed to all stake pools that created blocks during an epoch.

Incentivizing users to participate in staking and governance is not an exact science. There are examples of blockchains who have suffered low participation numbers and have switched to a model that pays participants.

Cardano's monetary expansion depends on a long-term commitment by stake pool operators to support the chain. It is the SPOs who run the cardano-node, which is the heartbeat of the network. The incentive system does not significantly change over time, and while staking rewards gradually depreciate, transaction fees should increase as adoption grows. SPOs can also receive rewards by providing similar support for sidechains and partner chains. More about that shortly.

Cardano's monetary policy focuses on two main points:

1. Staking rewards for those participating in the network as discussed above.
2. Funding the treasury.

Staking rewards come from two sources. Fees from every transaction and from all blocks produced during each epoch go into a virtual pot. A fixed percentage of the remaining ada reserves is also added to this pot every epoch. Ada reserves is the difference between total supply and circulating supply. That percentage (denoted ρ) is known as the monetary expansion. It is a protocol parameter currently set at 0.3%, but may be updated in future.

A set percentage of the pot is then sent to the treasury and the rest is used as epoch rewards.

The treasury is another important keystone of Cardano's monetary policy. The goal is that there will always be funds available to develop Cardano. The funds should be accessible through governance mechanisms where proposals are voted on by ada holders. Funds are regularly sent to the treasury to ensure it is always topped up.

There are many other parameters you can review online. We'll look at them in greater detail in future courses.


Crypto can be rife with jargon, especially in the NFT space, where terms like coins, tokens, currencies, assets, multi-assets..etc are often used interchangeably. Sometimes use cases overlap and tokens fit into multiple categories. A reminder we have a supporting glossary for this course which you can review as needed.

Almost everything in Cardano can be traced back to the research papers. Native Assets are no different, with the original concept discussed in the Native Custom Tokens in the Extended UTXO Model paper.

Cardano has the unique ability to create, interact with, and delete bespoke tokens (or 'assets') natively. When we say 'native', we mean that, in addition to sending and receiving the official currency ada, you may interact with custom assets right out of the box - without the need for smart contracts. Fungible and non-fungible tokens (NFTs) are both native assets treated as 'first class citizens', meaning they have the same capabilities as ada in every sense because the functionality is already built into the protocol. This reduces complexity, making it easier for developers, and opens up new uses. Cardano's native assets function based on a set of rules that govern the creation, issuance, and management of native tokens on the Cardano blockchain.

This design has broad ramifications, for example, all the security features that apply to ada, automatically apply to your token. Multi-asset support is written into the integration with centralized exchanges, so now it’s easy for exchanges to list your newly minted token. Also, everything that comes with the governance stack, the voting mechanics seamlessly work for your token as well. No code has to be rewritten, it’s a ‘batteries included’ turnkey solution.

The creation and transfer of native tokens cost a fraction of transaction fees on other chains. You can check how much something will cost in advance and it won’t spike later just because the network is busy. This predictability is referred to as determinism. Native tokens are scalable because they do not require the use of a separate layer for smart contracts. This makes it possible to transfer a large number of digital assets in one transaction to multiple wallet addresses. Native assets are flexible and can be customized to meet the specific needs of different dApps.

Native tokens are more secure because they are managed by the Cardano ledger itself, which makes them transparent and auditable. The policy is set by the user who wishes to mint the new asset. The node checks adherence to minting policies when a transaction is processed by running the code or checking for the required signatures. Transaction data must satisfy the minting policies of all assets the transaction is attempting to mint.

Native tokens represent value and act as an accounting unit, so they can be used for payments and transactions in the same way as ada is. While ada is used as Cardano’s main currency for fees and rewards today, there is a clear path laid out in a research paper (Babel Fees via Limited Liabilities) on how users can potentially pay transaction fees in native tokens in future. Cardano is designed so the eUTXO model and native asset design work seamlessly together with efficiency and robust security properties built in. Cardano’s design decisions enable unique features such as a token bundle which is a mix of tokens scoped under one or more minting policies. Any tokens can be bundled together, including ada. You can see how powerful this feature can be by reviewing some of the ‘records’ on eutxo.org

Unlike Ethereum’s ERC20 standard, native tokens do not require special transfer fees or additional event-handling logic to track transactions. With Ethereum, ether is an asset and ERC20 is a smart contract, and both compete for resources while at the same time being treated differently by the blockchain. ERC20 token creation requires manual modification of the contract standard, which opens the door for human error and likelihood of bugs. There have been billions of dollars lost due to security issues resulting from such designs.

Interoperability is defined as the ability of blockchain networks to talk to each other, enabling secure transactions, and transfer of digital assets and tokens. Mass adoption is also dependent on enabling interoperability with the legacy financial system, enabling users to onboard to, and exit from, the fiat currency world.

In addition to inventing the first provably secure proof-of-stake protocol called Ouroboros, Professor Aggelos Kiaysis and his fellow researchers introduced a whole gamut of interoperability protocols such as NIPoPoWs (Non-Interactive Proofs of Proof-of-Work) and sidechain protocols.

If the different blockchains and systems don't have a seamless way to communicate with each other, everything works in silos and potential user bases are diluted. Sometimes it makes business sense for traditional rivals to partner for mutual benefit. Take cloud service providers, for example. Oracle database is available on Microsoft Azure and Amazon Web Services although they compete in many areas.

Sidechains are a key enabler for interoperability. A sidechain is a blockchain in itself, linked to a main blockchain (the mainchain, or parent chain) through a two-way mechanism called a ‘bridge’. Digital assets from one chain can be utilized in another and the results shared back and forth. Multiple sidechains may be joined to a single parent chain, each of which can function in a different fashion. A sidechain can be thought of as just another blockchain, the difference between them is often philosophical, not technical. The sidechain typically aligns with the mainchain, but can have its own business logic, cryptocurrency, monetary policy, consensus rules, programming language, subset of users, smart-contract capabilities, stablecoins, use cases like NFTs, loyalty points, etc. Sidechains are suited to medium to low-risk protocols, where new, or growing ecosystems need a jump start, as the sidechain can leverage an existing mainchain’s security, liquidity, wallets, and user base. Sidechains can literally take a load off a layer 1 mainnet, all the while enjoying the veracity provided by its parent chain. Even if there is large transaction traffic on a sidechains, these transactions don’t need to be reconciled on the mainchain. A sidechain won’t eat up the resources from its parent mainchain.

As you might expect at this stage, a lot of deep thought and academic rigour went into Cardano’s architecture. Another example is in how rewards incentivize sidechain partnerships. Ada holders who delegate their stake get rewarded in ada, however, the same SPOs that power the mainchain, will also provide staking liquidity for sidechains. The result is, if the SPO you delegate to is also part of the sidechain SPO subset, you will also be rewarded in that sidechain’s native asset,in addition to your usual ada rewards.

The ‘Why Cardano’ essay from 2017 describes the vision for a layered architecture. The strategy and terminology was updated slightly in 2023. The new model would mean there would still be separation of layers. The Cardano Asset and Settlement Layer (CASL) will act as a proven, robust settlement layer for partner chains, while the Cardano Service Layers (CSL) mirrors the philosophy of microservices, or service oriented architecture.

You can think of Partner chains as an extension of the side chains concept. Midnight is muted to be the first of its kind. Midnight will be a 4th generation blockchain as it will enable data protection and follow a multi-resource consensus model, leveraging both proof-of-work and proof-of-stake simultaneously. Advancements in zero knowledge proofs will enable data and metadata to be protected. Blockchains can’t keep a secret today, Midnight aims to introduce this capability and with it a new world of use cases.

Partner Chains will have the flexibility to construct their own computation layers using modular components while still leveraging the CASL. Each (CSL) service layer can have its own distinct logic with unique tokenomics, consensus protocol, etc, but they will all have the same ‘common ancestor’ in the CASL.

This design will mean Cardano could potentially be the settlement layer for other blockchains. Security will be provided by Cardano’s SPOs as before, but now multi resource consensus will allow validators from other chains to contribute. The introduction of Babel fees (still in research) will allow chains to integrate smoothly as users will be able to transact in their own native currency, while Cardano SPOs can still be rewarded in ada.

One of the cornerstones of Cardano is decentralisation, but true decentralisation must be realised across three plains: block production, consensus networking and governance. Cardano has traditionally managed update proposals and trialled governance tooling through two mechanisms.

The Cardano Improvement Proposals (CIP) help steer the boat from a technical standpoint. Engineers and product designers propose reusable technical solutions to common problems.

The other mechanism is Project Catalyst, a community-driven innovation fund. Cardano holders can propose projects, review, comment and vote on them. Community funds are allocated to the most promising initiatives. Catalyst takes an experimental approach, and the process has been tweaked and improved over standalone funding rounds. Governance on Cardano is still in its infancy, and we are now in the phase of implementing on-chain mechanisms to realise the vision for the Age of Votaire. Many of the learnings taken from the Catalyst journey are fed into CIP-1694.

CIP-1694, named after the year of Voltaire’s birth, is a proposal for bootstrapping on-chain governance. Back when Cardano was formed, there was a tripartite structure with Emurgo, Cardano Foundation (CF) and IOG. It was always intended to transition to a members-based organization (MBO) that would manage the bureaucracy of protocol governance. Throughout 2023 and 2024, IOG and the CF ran workshops all around the globe to gather feedback and refine CIP-1694. To summarise, the proposal focuses on three different categories:

1. The idea of representation. Direct representation is where an ada holder personally votes, and delegated authority where you hand someone else your vote. In CIP 1694, this role is called a DRep, a delegated representative.
    
2. A constitution describes the guardrails for the system, to insure some degree of stability. For Cardano, this constitution can be drafted to be machine understandable, so once a voting mechanism is in place, the constitution can then be ratified, hashed and embedded into a transaction.
    
3. Institutions set standards and facilitate a review process by domain experts, acting as the custodians of knowledge and best practices.
    

One members based organization, or MBO, focussing on Cardano governance is called Intersect. It is an aggregation point for anyone interested to meet and debate issues, manage Cardano’s roadmap, facilitate the development of strategies to achieve key milestones, and attract suitable developers and entities to build tooling, services, critical infrastructure, etc. While Intersect is the anchor institution for Voltaire, it is just one. Another MBO is PRAGMA which attempts to foster an alternative open-source ecosystem for Cardano and other blockchains.

In summary, while liquid democracy is not a new concept, and constitutions have been written before, nothing on this scale has been attempted in the crypto space. The following are some of the key milestones for the Age of Voltaire:

- In Q4 of 2023, Cardano wallets Lace, Yoroi, and others announced integration into the Governance Tool (GovTool) for Voltaire testing within SanchoNet.
    
- The Interim Constitution was drafted, providing a framework for the Constitutional Committee to function during the bootstrapping phase.
    
- Throughout 2024, there was ongoing community consultation through another series of workshops to discuss and debate Cardano's Constitution. Feedback from the workshops was fed into the Constitutional Convention, which took place in Buenos Aries and Nairobi, Kenya in December 2024. Delegates representing over 50 countries voted in favour of the Constitution.
    
- The DRep Pioneer Program supports prospective candidates on understanding the DRep role, code of conduct, the delegation process, how to become a DRep, DRep rewards, engaging with the community among other topics.
    
- Intersect provides similar support for the Constitutional Committee, ensuring that members are trained for their roles and are able to execute effectively.
    
- There are several working groups and committees with different remits such as: the Membership and Community Committee, Technical Steering Committee, Open Source Committee, Parameter Committee, Vision Committee, Budget Committee, Product Committee and Cardano Civics Committee.
    
- The Chang upgrade in September 2024 was another Cardano milestone as it implemented a minimum viable on-chain governance. The Plomin upgrade followed in January 2025 where all on-chain governance actions were turned on. The constitution was subsequently ratified in an on-chain vote when a governance action was submitted and passed the required threshold.