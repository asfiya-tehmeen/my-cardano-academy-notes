# Scalability, Hydra, Tokenomics, Native Assets, Interoperability, Governance

---

## 1. Scalability

### What it means and how to measure it

- **Scalability** = a blockchain's ability to handle usage or adoption.
- It's not just TPS (transactions per second). TPS is probably the crudest metric because transactions come in all sizes and formats.
- Better to look at a range of metrics:
    - **Throughput**: quantity of data a system can process in a given length of time.
    - **Script execution time**: how long the CPU was busy.
    - **Finality**: time for a transaction to become immutable.
    - **Concurrency**: how much work different actors can do without interfering with each other.
    - **Actual transaction size.**
- Any blockchain can look fast with tiny transactions and no scripts.
- Some high-profile chains are centralized (e.g. a minority of validators control a disproportionate share of stake). It's easy to compromise on decentralization and then boast astronomical TPS.

### Throughput on Cardano

- Throughput means something different in a **UTXO** system than in an **account-based** one.
- TPS on Cardano is more nuanced still because of **native assets**: eUTXO lets **hundreds or even thousands of native assets** move in a **single transaction**.
- Nearly everything on Cardano is a transaction, and resources get consumed by things like: transferring ada, issuing assets, executing smart contracts, voting, adding metadata.
- A more accurate metric is therefore **TPT (transactions per transaction)**.
- To see how transactions work, visit **eutxo.org**, a blockchain explorer showing a live view of blocks and their contents as they're created. _(The source writes this as "eUTtxO.org" once and "eutxo.org" later, so I've used the latter.)_

### Scaling approaches

- **No magic bullet.** It's done by tweaking parameters and combining solutions, which fall into two categories:
    - **Layer 1**: upgrades applied to the mainchain (i.e. Cardano).
    - **Layer 2**: offloading workloads, extending functionality, integrating other blockchains via **sidechains, ZK rollups and state channels**.
- Another way to split them:
    - **On-chain:** block size increases, pipelining, input endorsers, parameter adjustments, Plutus script enhancements, node enhancements, on-disk storage improvements.
    - **Off-chain:** sidechains, partner chains, **Hydra**, off-chain computing, **Mithril**.
- _To be covered in more depth in future courses._

### Blockchain size (bloat)

- Blockchains can store data indefinitely. Every transaction is logged regardless of relevance, and the volume grows as TPS rises.
- A bloated chain means **slower wallet sync times**. Analogy: flooding your basement, which makes life difficult in the long term.
- Cardano's architecture moves a lot of **computation off-chain** and stores the **minimum on the mainchain**.
- **Size comparison:**

|Chain|Size|
|---|---|
|Bitcoin|passed 0.5 TB in late 2023|
|Ethereum|wallets must download over 1 TB to sync|
|Cardano|177 GB|
|Solana|3.8 TB|

---

## 2. Hydra (Layer 2 for Cardano)

- Earlier we saw the Lightning Network on Bitcoin. **Hydra** is a Layer 2 scaling solution tailored for Cardano.
- Uses **isomorphic state channels** to increase throughput, cut transaction fees and reduce storage needs.
- Developed through principled, evidence-based research. Makes it easier to transact off-chain while using the **main-chain ledger for secure settlement**.

### Decoding the jargon

- **Isomorphic**: "iso" = equal (like isometric), "morphic" = shape/form. So **same structure and properties**.
- **State channels**: extend payment channels to also support **smart contracts** off-chain. Participants can, besides normal payments, run scripts for complex logic off-chain, then commit the result back to Layer 1.

### How it works

- Participants **lock funds into a smart contract**.
- They transact with each other in the state channel, off-chain, however suits their use case.
- The outcome is then **settled on-chain**, without needing the full off-chain transaction history.
- Developers can reuse Cardano's proven infrastructure to build wallets and dApps that talk to the Layer 2 system, which cuts the learning curve a lot.

### Other points

- Developed in collaboration with the Ouroboros protocol and the Cardano ledger, but can also be used with other systems that have the same properties as Cardano.
- Replicates the main chain's functionality with minimal friction for users, while still allowing a **different fee structure and timing constraints** on Layer 2.
- **Hydra vs Lightning:** Hydra fits Cardano well because eUTXO and smart contracts let developers build rich isomorphic state channels. Lightning faces friction because **Bitcoin doesn't support programmability**.

---

## 3. Tokenomics and Monetary Policy

### Tokenomics

- **Tokenomics** = the economic model of a coin or token: total supply, circulating supply, initial distribution, among other things.
- Cardano had a very fair distribution compared with counterparts: **80% of ada owned by the public**.

### Supply

- **Total supply: 45 billion ada** (the amount that will ever exist).
- **Circulating supply: ~35 billion.**
- **Ada reserves = total supply − circulating supply.**

### Monetary policy goals

- Carefully designed to keep inflation **low long term**.
- Done by setting a parameter that controls the **maximum percentage of ada that can be released in a given period**.
- Result of academic research on the game theory of inflation, including analysis of how circulating supply affects overall value.
- Designed to **incentivize SPOs** to take part in staking, for long-term sustainability.
- Delegators and SPOs are rewarded each epoch with a proportion of ada **plus transaction fees**.

### Fees

- Transaction fees are **deterministic** (predictable) for developers.
- Fees **don't go straight to the block producer**. They're pooled and distributed to **all stake pools that made blocks in that epoch**.

### Incentives and long-term commitment

- Incentivizing staking and governance participation isn't an exact science. Some chains had low participation and switched to a model that **pays participants**.
- Cardano's monetary expansion relies on SPOs' long-term commitment. They run the **cardano-node**, "the heartbeat of the network".
- The incentive system doesn't change much over time. **Staking rewards gradually depreciate, but transaction fees should rise as adoption grows.**
- SPOs can also earn rewards by supporting **sidechains and partner chains** (more later).

### Two main points of the policy

1. **Staking rewards**
2. **Funding the treasury**

### Where staking rewards come from

- Two sources feed a virtual **pot** each epoch:
    1. Fees from every transaction and all blocks produced in the epoch.
    2. A fixed percentage of the **remaining ada reserves**, called the **monetary expansion**, denoted **ρ (rho)**. A protocol parameter, **currently 0.3%**, may be updated in future.
- A set percentage of the pot goes to the **treasury**; the rest is paid out as **epoch rewards**.

### Treasury

- Goal: **always have funds available to develop Cardano**.
- Funds accessible via governance: proposals voted on by ada holders.
- Regularly topped up.
- Many other parameters can be reviewed online (future courses).

---

## 4. Native Assets

### Terminology note

- Crypto is full of jargon, especially in NFTs: coins, tokens, currencies, assets, multi-assets are often used interchangeably. Use cases overlap and tokens can fit several categories. _(The course has a supporting glossary.)_

### What they are

- Origin: research paper **"Native Custom Tokens in the Extended UTXO Model"**.
- Cardano can **create, interact with and delete bespoke tokens (assets) natively**.
- "Native" = besides sending/receiving ada, you can use custom assets **out of the box, without smart contracts**.
- **Fungible tokens and NFTs** are both native assets and are **"first class citizens"**: same capabilities as ada, because the functionality is built into the protocol.
- This reduces complexity for developers and opens new uses.
- Governed by rules for creation, issuance and management of native tokens.

### Benefits

- **Inherited security:** all security features that apply to ada automatically apply to your token.
- **Exchange integration:** multi-asset support is written into integration with centralized exchanges, so listing a newly minted token is easy.
- **Governance:** voting mechanics work for your token too.
- **No rewriting code**: "batteries included", turnkey.
- **Cheap:** creating and transferring native tokens costs a fraction of fees on other chains.
- **Predictable (determinism):** you can check the cost in advance and it won't spike because the network is busy.
- **Scalable:** no separate smart contract layer needed, so many assets can go to multiple wallet addresses in one transaction.
- **Flexible:** customizable for different dApps' needs.
- **More secure:** managed by the Cardano ledger itself, so transparent and auditable.

### Minting policies

- The policy is set by whoever mints the asset.
- When processing a transaction, the node checks adherence to minting policies by **running the code or checking for required signatures**.
- Transaction data must satisfy the minting policies of **all assets it's trying to mint**.

### Use as money

- Native tokens represent value and act as an accounting unit, so they can be used for payments like ada.
- Today ada is the main currency for fees and rewards, but a research paper (**"Babel Fees via Limited Liabilities"**) lays out a path for users to **pay fees in native tokens** in future.
- eUTXO and native assets are designed to work together with efficiency and strong security.
- **Token bundle**: a mix of tokens scoped under one or more minting policies. Any tokens can be bundled, **including ada**. See the "records" on eutxo.org for examples.

### Cardano vs Ethereum ERC-20

- Native tokens need **no special transfer fees or extra event-handling logic** to track transactions.
- On Ethereum, **ether is an asset and ERC-20 is a smart contract**. They compete for resources and are treated differently by the chain.
- ERC-20 creation needs **manual modification of the contract standard**, which allows human error and bugs.
- **Billions of dollars** have been lost to security issues from such designs.

---

## 5. Interoperability

### Why it matters

- **Interoperability** = the ability of blockchain networks to talk to each other, enabling secure transactions and transfer of digital assets and tokens.
- Mass adoption also needs interoperability with the **legacy financial system**, letting users onboard to and exit from the fiat world.
- **Prof. Aggelos Kiayias** and fellow researchers invented Ouroboros and also introduced a whole range of interoperability protocols, such as **NIPoPoWs (Non-Interactive Proofs of Proof-of-Work)** and **sidechain protocols**. _(The source spells his surname "Kiaysis"; the usual spelling is Kiayias.)_
- Without seamless communication, everything works in silos and potential user bases get diluted.
- Sometimes rivals partner for mutual benefit. Example: **Oracle database** is available on **Microsoft Azure** and **Amazon Web Services** even though they compete in many areas.

### Sidechains

- A **sidechain** is a blockchain in its own right, linked to a main (parent) chain through a **two-way bridge**.
- Assets from one chain can be used in another, with results shared back and forth.
- **Multiple sidechains** can attach to one parent chain, each working differently.
- The difference between a sidechain and any other blockchain is often **philosophical, not technical**.
- Typically aligns with the mainchain but can have its own: business logic, cryptocurrency, monetary policy, consensus rules, programming language, subset of users, smart contract capabilities, stablecoins, and use cases like NFTs or loyalty points.
- Suited to **medium to low-risk protocols**, where new or growing ecosystems need a jump start. They can borrow the mainchain's **security, liquidity, wallets and user base**.
- Take load off the Layer 1 mainnet while benefiting from the parent chain's veracity.
- Even heavy traffic on a sidechain **doesn't need to be reconciled on the mainchain**, so it doesn't eat the parent's resources.

### Rewards for sidechain partnerships

- Delegators get ada rewards. The **same SPOs that run the mainchain also provide staking liquidity for sidechains**.
- So if your SPO is also in the sidechain's SPO subset, you're **also rewarded in that sidechain's native asset**, on top of normal ada rewards.

### Layered architecture: CASL and CSL

- The **"Why Cardano" essay (2017)** described a vision of layered architecture. Strategy and terminology were updated slightly in **2023**.
- Layers stay separate:
    - **CASL (Cardano Asset and Settlement Layer)**: proven, robust settlement layer for partner chains.
    - **CSL (Cardano Service Layers)**: mirrors the philosophy of **microservices / service-oriented architecture**.
- Each CSL can have its own logic, tokenomics, consensus protocol etc., but all share the **same "common ancestor" in CASL**.
- Partner chains can build their own computation layers from modular components while still using CASL.
- Cardano could potentially be the **settlement layer for other blockchains**.
    - Security still provided by Cardano SPOs, but **multi-resource consensus** will let validators from other chains contribute.
    - **Babel fees** (still in research) would let chains integrate smoothly: users transact in their own native currency while Cardano SPOs are still rewarded in ada.

### Partner chains and Midnight

- **Partner chains** = an extension of the sidechain concept.
- **Midnight** is mooted to be the first of its kind and a **4th generation blockchain**:
    - enables **data protection**
    - uses a **multi-resource consensus** model, with **proof of work and proof of stake at the same time**
    - advances in **zero knowledge proofs** protect data and metadata
    - "Blockchains can't keep a secret today", and Midnight aims to change that, opening up new use cases

---

## 6. Governance

### Three planes of decentralization

- Decentralization has to happen on three planes: **block production, consensus networking, governance**.
- Cardano has so far managed update proposals and trialled governance tooling through two mechanisms:

**Cardano Improvement Proposals (CIPs)**

- Steer the technical direction. Engineers and product designers propose reusable technical solutions to common problems.

**Project Catalyst**

- Community-driven **innovation fund**. Holders propose projects, review, comment and vote. Funds go to the most promising ones.
- Experimental; the process has been tweaked over successive funding rounds.
- Governance on Cardano is still young. The current phase is implementing on-chain mechanisms for the **Age of Voltaire**. Lessons from Catalyst feed into **CIP-1694**.

### CIP-1694

- Named after the **year of Voltaire's birth**. A proposal for **bootstrapping on-chain governance**.
- Background: Cardano began with a tripartite structure (Emurgo, CF, IOG). The plan was always to move to a **members-based organization (MBO)** to manage the bureaucracy of protocol governance.
- Through **2023 and 2024**, IOG and the CF ran workshops worldwide for feedback to refine it.
- Three categories:
    1. **Representation**
        - **Direct representation**: an ada holder votes personally.
        - **Delegated authority**: you hand your vote to someone else.
        - In CIP-1694 this role is a **DRep (delegated representative)**.
    2. **Constitution**
        - Sets the guardrails for the system, to ensure some stability.
        - Can be drafted to be **machine understandable**: once voting is in place, the constitution can be **ratified, hashed and embedded into a transaction**.
    3. **Institutions**
        - Set standards and run a review process by domain experts, acting as custodians of knowledge and best practice.

### MBOs

- **Intersect**: an MBO focused on Cardano governance.
    - A meeting and debating point for anyone interested.
    - Manages Cardano's roadmap, helps develop strategies for key milestones, and attracts developers/entities to build tooling, services, critical infrastructure etc.
    - The **anchor institution for Voltaire**, but only one of several.
- **PRAGMA**: another MBO, trying to foster an **alternative open-source ecosystem** for Cardano and other blockchains.
- Overall: liquid democracy isn't new and constitutions have been written before, but **nothing at this scale has been tried in crypto**.

### Age of Voltaire milestones

- **Q4 2023**: wallets **Lace, Yoroi** and others announced integration with the **Governance Tool (GovTool)** for Voltaire testing on **SanchoNet**.
- An **Interim Constitution** was drafted, giving a framework for the **Constitutional Committee** to function during bootstrapping.
- **Throughout 2024**: more community workshops on the Constitution. Feedback went into the **Constitutional Convention**, held in **Buenos Aires and Nairobi, Kenya in December 2024**. Delegates from **over 50 countries** voted in favour of the Constitution.
- **DRep Pioneer Program**: supports prospective DReps on the role, code of conduct, the delegation process, how to become a DRep, DRep rewards, engaging with the community, and more.
- **Intersect** gives similar support to the **Constitutional Committee** so members are trained and can do the job well.
- **Working groups/committees:** Membership and Community Committee, Technical Steering Committee, Open Source Committee, Parameter Committee, Vision Committee, Budget Committee, Product Committee, Cardano Civics Committee.
- **Chang upgrade, September 2024**: implemented a **minimum viable on-chain governance**.
- **Plomin upgrade, January 2025**: **all on-chain governance actions turned on**.
- The constitution was then **ratified in an on-chain vote**, after a governance action was submitted and passed the required threshold.

---

## Quick reference: key terms

- **Throughput / finality / concurrency**: data processed over time / time to immutability / work done without interference.
- **TPT**: transactions per transaction, a better metric than TPS for Cardano.
- **Layer 1 / Layer 2**: mainchain upgrades / offloading and extending (sidechains, ZK rollups, state channels).
- **Hydra**: Layer 2 using isomorphic state channels.
- **Isomorphic**: same structure and properties.
- **State channel**: payment channel that also supports off-chain smart contracts.
- **Mithril**: off-chain scaling solution (covered later).
- **ρ (rho)**: monetary expansion, currently 0.3% of reserves per epoch.
- **Ada reserves**: total supply minus circulating supply.
- **Native asset**: token handled by the ledger itself, no smart contract needed.
- **Token bundle**: mix of tokens under one or more minting policies, can include ada.
- **Babel fees**: (in research) paying fees in native tokens.
- **Determinism**: predictable fees/outcomes.
- **NIPoPoWs**: Non-Interactive Proofs of Proof-of-Work.
- **Sidechain / partner chain**: blockchain linked to a mainchain via a two-way bridge / extension of that idea.
- **CASL / CSL**: Cardano Asset and Settlement Layer / Cardano Service Layers.
- **Midnight**: mooted 4th gen partner chain, privacy via zero knowledge proofs.
- **CIP / CIP-1694**: improvement proposals / on-chain governance proposal.
- **DRep**: delegated representative.
- **MBO**: members-based organization (Intersect, PRAGMA).
- **GovTool / SanchoNet**: governance tool / governance testnet.
- **Chang / Plomin**: Sept 2024 minimum viable governance / Jan 2025 full on-chain governance actions.