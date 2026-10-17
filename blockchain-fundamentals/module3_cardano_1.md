# Origins, Roadmap, Ouroboros, Staking, eUTXO, Smart Contract Languages

---

## 1. Origins of Cardano

### The three "genesis" entities

Three entities have traditionally propped up Cardano.

**Input Output Global (IOG)** (formerly Input Output Hong Kong)

- Co-founded in **2015** by **Charles Hoskinson and Jeremy Wood**.
- The development and science arm of Cardano. Since 2015 it has focused on protocol development and academic research.
- More recently pivoted to a **venture studio** model, with spinoff companies working on:
    - **Lace** light wallet (lace.io)
    - **RealFi** (realfi.io)
    - the **Midnight** partner chain
    - other critical infrastructure projects
- Cardano went live in **2017**. Built on peer-reviewed academic research, and it has had **100% uptime** since.

**Cardano Foundation (CF)**

- Based in **Zug, Switzerland**.
- Set up as the **legal custodian of the Cardano brand** and a contributor to Cardano's governance.
- Statutory purpose: support the adoption and advancement of Cardano as a **public digital infrastructure**.
- Core activities:
    - providing utilities to the ecosystem
    - developing enterprise infrastructure tooling
    - strengthening operational resilience and regulatory clarity
    - driving education through different initiatives
- Part of this is facilitating interactions with stakeholders: the immediate ecosystem, plus international ones like standard setters, lawmakers and regulators.

**Emurgo**

- Focused on **Asia and Africa**.
- The **commercialization arm** of Cardano.
- Works on: education, fintech infrastructure, the **Yoroi** wallet, ecosystem growth, smart contract audits, and a social network called **Cardano Spot**.

### Ecosystem size

- Now dozens of companies and hundreds of projects building on Cardano (too many to list). See the **Showcase** section of the **Cardano Developer Portal**.
- _(The source text has a placeholder here: "link the latest essential cardano weekly stats". Worth adding the link yourself.)_

### Cardano's philosophy

- Mission from the start: **improve on previous generations and build for the long term**.
- Vitalik Buterin said Ethereum favours "more heuristic arguments as it's trying to do more faster". Cardano went with a **"first principles" peer-reviewed academic research** approach instead:
    - rigorous processes, formal methods, mathematical specs and proofs
    - aim: **high-assurance software**
    - over **200 research papers** published and scrutinised at top cryptography conferences
- **Open-source, patent-free**: research papers, formal specs and code repos are available to all. Anyone with the right technical skills can check the claims.
- Other projects have borrowed heavily from IOG's research in their protocol design.
- Unlike the many projects that are just forks of existing blockchains, much of Cardano is **custom built from first principles**.

### Three key areas for mass adoption

**1. Scalability**

- Bitcoin and Ethereum were landmark achievements but both have shortcomings.
- Bitcoin: only **7 transactions per second**.
- Ethereum: struggles with demand. At a certain capacity, system bloat sets in, performance becomes unpredictable and fees spike intermittently. The same transaction can cost different gas fees depending on demand.
- Cardano wants to fix this and mirror protocols like **BitTorrent**, where performance **scales as new users join**.

**2. Interoperability**

- Mobile devices only work because of layers of interoperability standards:
    - **GSM** (Global System for Mobile Communications): lets phones talk across networks and jurisdictions
    - **Wi-Fi** standard: connectivity and faster speeds
    - **TCP/IP**: suite of protocols letting computers communicate on the internet
- The future of blockchain is **multi-chain**; many dApps and tokens already operate cross-chain.
- Cardano has multiple solutions moving from research papers to full implementation.

**3. Governance** (sometimes called sustainability)

- Bitcoin and Ethereum have both hit problems scaling because they have **no decision-making mechanisms to manage change**.
- With millions of users, it's not viable or healthy for a small **"one pizza" core team** to dictate outcomes.
- Can lead to traumatic splits, e.g. Bitcoin's **"Big blocks versus SegWit"** debate, which ended in a hard fork creating **Bitcoin Cash and Bitcoin**.
- Governance isn't a sexy topic but is arguably essential for a blockchain to last. Open questions:
    - How do we decide on an important parameter change?
    - What happens when quantum computers arrive?
    - How does a fledgling decentralized protocol decide on a roadmap?
- **Funding:** money has to come from somewhere for startups to breathe.
- **Tragedy of the commons:** users agree essential infrastructure and critical updates are needed, but there's no mechanism to apply for or approve development funding.
- **Cardano's answer:**
    - Community sustains development by submitting and voting on funding proposals in **Project Catalyst**.
    - Community controls the **treasury**, which is regularly topped up from various sources.
    - Clear plan for **end-to-end on-chain governance**.

---

## 2. Cardano Development Milestones

- Named after **Gerolamo Cardano**, an influential Renaissance mathematician.
- The roadmap has **five major eras**, each named after a historical figure: **Byron, Shelley, Goguen, Basho, Voltaire**.
- Eras overlap in places and have some interdependencies.

|Era|Named after|Focus|
|---|---|---|
|**Byron**|Lord Byron (romantic poet)|Bootstrapping the network, transacting in ada|
|**Shelley**|Percy Shelley (romantic poet)|Decentralization, stake pools|
|**Goguen**|Joseph Goguen (American computer scientist/academic)|Smart contracts, multi-asset ledger|
|**Basho**|Matsuo Basho (Japanese poet)|Scalability, interoperability|
|**Voltaire**|Voltaire (French philosopher)|On-chain governance|

### Byron

- Initial development phase. Focus: **bootstrapping the network** so users could transact in **ada**.
- **Ada** is named after Lord Byron's daughter **Ada Lovelace** (19th century mathematician and pioneering programmer).
- **1 ada = 1 million lovelaces.**
- **Fixed supply: 45 billion ada.**
- Every ada holder is incentivized to **stake** their ada, which helps secure the network, and to take part in governance (more later).
- Holders used the **Daedalus** full node wallet to store, send and stake ada on the **incentivized testnet (ITN)**.
- The full node wallet was important for bringing security and stability during bootstrapping.
- **Light wallets** (most people use these now):
    - Smaller than a full node wallet; doesn't take part in block validation in the same way.
    - Can query the blockchain but doesn't store the entire chain state.
    - Much faster, but relies on a **third party** to deliver (query) blockchain data.

### Shelley

- **Decentralization** phase. Introduced **stake pools** to boost Cardano's security and scalability. Users could now earn rewards by staking ada to pools.
- **31 March 2021**: block production became **fully decentralized**. Stake pool operators (SPOs) began producing **100% of new blocks**.
- The **"d" (decentralization) parameter** was later retired, making the network **irreversibly decentralized**.
- Currently **3,000+ active pools**, with **over 60% of ada staked**. One of the most decentralized cryptocurrencies.

### Goguen

- Introduced **programmability** and smart contracts. Developers could now build **dApps**.
- **Plutus Platform** introduced: smart contracts written in **Haskell** to guarantee **deterministic outputs**.
- Core improvements, most significantly the **multi-asset ledger**, which lets users **mint new natively supported tokens**.
    - Supports fungible and non-fungible tokens.
    - Enables new digital assets on Cardano and **tokenization of many types of physical assets**.

### Basho

- Focus: **scalability** and **interoperability**.
- About boosting network performance to support mass adoption as transaction volumes grow and dApps need more resources.

### Voltaire (the governance era)

- Until now Cardano has used **Cardano Improvement Proposals (CIPs)** to manage change, plus **Project Catalyst** (an innovation fund where ada holders propose ideas, vote and receive funding).
- Voltaire brings **voting and other governance mechanisms completely on-chain** (more later).

### Eras run in parallel

- Although they look sequential on the roadmap, some are developed in parallel.
- Example: we're currently in the Age of Voltaire, but key scalability solutions like **"input endorsers"** will only come in after an **on-chain vote**, since they need a significant protocol change.

### Seamless upgrades: the Hard Fork Combinator (HFC)

- **Big differentiator.** On most blockchains upgrades happen via **hard forks**, which are traumatic for the community: existing protocol disabled, new rules introduced, chain restarted with all history destroyed.
- Cardano does it differently. The **HFC** allows a seamless transition to a new protocol while **preserving block history** and causing minimal inconvenience.
- Designed to integrate many protocols without major changes.
    - **Byron and Shelley** era blocks have already been combined in the Cardano blockchain.
    - For future hard fork events, **Basho and Voltaire** blocks will be combined too, all as a single property.
- HFC keeps proving itself, with more gradual, iterative upgrades planned. Negligible, if any, user disruption.

---

## 3. What is Ouroboros?

### The name

- In Greek mythology, **Ouroboros** is a circular symbol of a snake swallowing its tail: wholeness or infinity of time flowing back into itself in an eternal cycle of life, death and rebirth.
- In blockchain terms: the protocol **constantly feeds itself from previous epochs and regenerates**, like eating its own tail.

### What it is

- **First provably secure proof-of-stake protocol.** One example of Cardano's meticulous peer-reviewed approach.
- Same strict security guarantees as proof-of-work chains like Bitcoin.
- Based on foundational research papers which found it **more robust and adaptive to attacks than previous Byzantine fault tolerant (BFT) protocols**.
- **Nakamoto Consensus** (after Satoshi) = Proof-of-Work + the "longest chain" rule.
- Ouroboros achieves **Nakamoto-style consensus** but with proof of stake:
    - Bitcoin-level robustness
    - **magnitudes more energy efficient**
    - **faster**
    - **fairer rewards system**
- Built on an innovative **game theoretic design** that discourages one entity gaining too much control and avoids **plutocracy**.

### Epochs and slots

- Time on Cardano is measured in **epochs and slots**.
- An **epoch** = a fixed number of slots, currently lasting **5 days**.
- For each slot, stake pools are randomly chosen as the **slot leader** to produce one or more blocks. Blocks are propagated to the network within the allocated slot time.
- Reliable randomness in slot leader selection is crucial: prevents network attacks and incentivizes honest stakeholders.
- Randomness comes from a **Verifiable Random Function (VRF)**: a major cryptographic breakthrough in **1999**, still widely used. It produces a random output with a proof anyone can use to verify the result.
- When judging a stake pool's performance, zoom out: it'll get more slots in some epochs and fewer in others, but it **averages out over the longer term**.

### Reliability

- Rigorous scientific approach plus proven track record makes Cardano a reliable base for **enterprise-grade** solutions.
- **100% uptime**, second only to Bitcoin (which launched years earlier). Other chains have well-documented hacks, outages and restarts.

### Energy use

- PoS needs a fraction of the power of PoW.
- **Cambridge Bitcoin Electricity Consumption Index**: the hardware running Bitcoin uses as much energy per year as a country like **Norway or Sweden**.
- Cardano's ethos: be as inclusive as possible, low barrier to entry. Stake pools have been run on a **Rock Pi** as far back as **2019**.

---

## 4. Staking on Cardano

### What is staking?

- Crucial for securing the network. **Ada holders delegate their funds to a stake pool and earn staking rewards.**
- Any ada holder can run their own node, which acts as a validator (processes transactions, adds blocks). These operators are **stake pool operators (SPOs)**.
- More ada staked = stronger network.
- Pools get rewards **after each epoch**, and some is passed on to delegators.
- **Timing:** when you delegate, your stake becomes **active two epochs later**. After that, rewards go **straight into your wallet every 5 days**. Hence staking rewards are often called **"passive income"**.

### Why Ouroboros staking is "best in class"

- **No slashing** (no losing some or all of your stake as punishment for dishonest behaviour).
- **No lock-up (bonding) periods.**
- Rewards distributed automatically every epoch; **funds always accessible**.
- **Non-custodial**: you have sole custody of your ada and you alone are responsible for securing your wallet.
- Your stake is **never at risk** of being taken by the SPO or a third party. (Not always true on other PoS chains.)

### Decentralization by design

- **3,000+ globally distributed stake pools.**
- Architecture uses **economic incentives** to stimulate decentralization.
- Pools naturally want to grow: more delegated stake = more blocks produced.
- The network is configured to stop single pools getting too big. Several parameters aim to find the best balance of stake across an ideal number of pools.
- **Saturation:** if a pool attracts more delegated stake than a given threshold, its payout falls. Once saturated, more delegated stake **no longer increases rewards**.
- Ideal outcome: a set number of pools of roughly equal size. Rarely exactly achieved, but enough to motivate most people to act honestly out of self-interest (to maximise rewards).
- Nobody's stake is ever revoked, but you might not earn full rewards if you try to game the system.

### SPOs are the backbone

- Their nodes (servers) add blocks and validate transactions.
- An SPO maintains the hardware behind the blockchain and is rewarded based on **stake in the network and pool performance**.
- Staking participation on Cardano is very high compared with other chains.
- Cardano uses the stake pool model to deliver some interoperability and governance features (coming up). SPOs effectively become **infrastructure providers** for rolling out new features released in new node versions.

---

## 5. Accounting models: Account vs UTXO vs eUTXO

### Background

- Businesses need a balance sheet to keep an accurate record of cash in/out, profit and other key metrics. Ledgers have been used in **double-entry bookkeeping since the 13th century**.
- Blockchain introduced the **shared distributed ledger**: an immutable record of all transactions.
- Networks need an accounting model to record who owns which coins and which are spent/unspent.

### Account model

- Explained with a bank: your balance is a single figure, updated on deposits and withdrawals. Transactions are debits and credits on different users' accounts.
- Account-based blockchains work the same way, except the ledger is **distributed across many nodes**.
- They track **updates to balances, not the actual coins**. Balances are stored as a **global state**, kept by each node and updated with every transaction.
- Popular model. First introduced with **Ethereum**; also used by others such as **Algorand**.

### UTXO model (unspent transaction output)

- "Cash in, cash out" analogy: at a book shop, paying with physical notes and coins. Each purchase hands over specific notes and coins, and your balance is what you have left.
- In blockchain, individual notes and coins (**UTXOs**) are tracked to represent your balance.
- **Bitcoin** uses UTXO.

### eUTXO (extended UTXO), Cardano's model

- Adds **programmability** to Bitcoin's proven UTXO model. Smart contracts let developers build dApps with custom logic while keeping security.
- **Metadata and scripts are bundled together in a single transaction** for greater throughput.
- Transaction verification is simpler, so you can **predict the outcome, including the cost**.
- Transactions can be verified **locally, off-chain**, with no dependence on the rest of the network. Developers can focus on the transaction and its inputs.
- **Failed transactions are not charged a fee** (unlike Ethereum).
- Can process **multiple transactions from a single transaction**, which changes the context for metrics like transactions per second.
- Users can send **multiple assets to several wallets in one transaction**, cutting fees further.
- _"Transactions per transaction" concept to be covered in a future video._

---

## 6. Programming on Cardano

Plutus and Marlowe were the main languages in the early years.

### Plutus

- A **platform** providing infrastructure and tools for writing smart contracts in **Haskell**. "Plutus" and "Haskell" are often used interchangeably. "Coded in Plutus" really means coding in Haskell using the Plutus Framework.
- The Plutus Framework lets developers create dApps that interact with a distributed ledger with scripting capabilities.
- More than a language: supports dApp development **end to end** (writing scripts, testing, runtime support, verification).
- **Three main components:**
    - **Untyped Plutus Core (UPLC)**: the "machine code" of the Cardano ledger
    - **PlutusTx**: plugin that compiles Haskell into UPLC (the on-chain component)
    - **Plutus Application Framework**: tools for writing smart contracts in Haskell
- **Three key concepts** to become a proficient Cardano developer:
    - the eUTXO model
    - **on-chain code** (Plutus Core), which runs on the blockchain
    - **off-chain code**, which runs on the user's device

### Marlowe

- Simple language for writing **financial smart contracts** on Cardano.
- Named after Elizabethan poet, dramatist and spy **Christopher Marlowe**.
- Limited to financial applications; **not Turing-complete**.
- A **DSL (domain-specific language)** for finance experts rather than programmers.
- Can code in Marlowe directly or use **Blockly**, a visual drag-and-drop tool that connects blocks representing the contract's components.

### You don't need Haskell

- Haskell programs on the Plutus platform compile to UPLC. The ledger only understands Plutus Core, but devs don't write that low-level language day to day.
- A growing list of **high-level languages compile to UPLC**.
- Developers want to use their favourite language, especially for the off-chain part (typically the biggest part of a dApp).
- Cardano is implemented in Haskell, but **UPLC is what actually executes**, so there's no reliance on Haskell.

### Aiken

- Named after mathematician **Howard Aiken**.
- A **functional DSL written in Rust**, open source.
- Unlike Haskell, built specifically for Cardano. Emphasis on **developer experience**, with "batteries included" state-of-the-art tooling. Inspired by modern languages like **Rust, Elm and Gleam**.
- Lean, opinionated, minimal configuration. Works out of the box; language-wide standards enforced by the compiler.
- Developers say it's easy to learn and you can get started in minutes. "Keep it simple" approach.
- By design, scripts support fewer features than general-purpose Turing-complete languages. It's a small language (not a high-level general-purpose one) built to produce **small, efficient on-chain scripts** that integrate with most languages off-chain.
- **State of the Cardano Developer Ecosystem 2023** survey: "Aiken users exhibit a tendency for Rust in off-chain scenarios."
- Praised for **Rust-like syntax** while keeping Haskell's strengths as a functional language. Many devs report big performance gains (faster, more efficient contracts).
- Supports **blueprint stub generation** (templates for different programming languages), making integration with off-chain components easy.

### Other options

|Tool|What it is|
|---|---|
|**Helios**|DSL compiling to Plutus Core. Built from the ground up for Cardano. Functional, very similar to **TypeScript**.|
|**OpShin**|Cardano smart contracts in a strict subset of **Python** (valid but restricted Python3).|
|**Plutarch**|Typed **eDSL (embedded DSL) in Haskell** for efficient Plutus Core validators. Not a new language: plain Haskell, no restrictions.|
|**plu-ts**|Library for writing Cardano software entirely in **TypeScript**.|
|**Scalus**|**Scala** implementation of Plutus.|

### Development culture and enterprise tooling

- Unlike chains that "move fast and break things", Cardano sticks to a deliberate, careful, methodical strategy. Despite this relative conservatism, its **GitHub repos were very active in 2021, 2022 and 2023**.
- More options for newcomers as adoption grows. Java is still the favourite for many enterprise developers, so the **Cardano Foundation** has written tools and services in **Java** and released them open source to encourage collaboration.
- Example: the **Identity Wallet**, a **W3C-compatible** mobile wallet for managing **self-sovereign identities** across Cardano and other blockchains. Supports multiple standards and integrates **KERI (key event receipt infrastructure)** for interoperability, fitting a broad range of use cases and encouraging enterprise adoption.

---

## Quick reference: key terms

- **IOG**: Input Output Global, development/science arm.
- **CF**: Cardano Foundation (Zug), brand custodian.
- **Emurgo**: commercial arm (Asia/Africa), Yoroi wallet.
- **Ada / lovelace**: 1 ada = 1,000,000 lovelaces; supply 45 billion.
- **Byron / Shelley / Goguen / Basho / Voltaire**: the five eras.
- **ITN**: incentivized testnet.
- **Daedalus**: full node wallet. **Light wallet**: fast but depends on a third party for data.
- **HFC**: Hard Fork Combinator, seamless upgrades that preserve history.
- **Ouroboros**: first provably secure PoS protocol.
- **Epoch**: 5 days (fixed number of slots). **Slot leader**: pool picked to make blocks for a slot.
- **VRF**: Verifiable Random Function (1999).
- **SPO**: stake pool operator.
- **Saturation**: point where extra delegation stops raising a pool's rewards.
- **eUTXO**: extended UTXO, with scripts and metadata in one transaction.
- **UPLC**: Untyped Plutus Core, the ledger's "machine code".
- **Plutus / Marlowe / Aiken / Helios / OpShin / Plutarch / plu-ts / Scalus**: smart contract languages and tools.
- **Project Catalyst**: community innovation fund. **CIPs**: Cardano Improvement Proposals.