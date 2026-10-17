
The **Cardano Foundation (CF)** has released an **open source rewards calculation** to promote transparency and community involvement for a stronger network. First, a recap of how staking works.

---

## 1. Staking recap

### PoS vs PoW

- In both PoS and PoW, nodes compete to produce blocks, and being selected is like a **lottery**.
    - **PoW:** hashing power sets your odds.
    - **PoS:** the **number of tokens** you control sets your odds.
- General idea: a mechanism elects **one actor at a time** to produce a block.
- Cardano's PoS algorithm **pseudo-randomly selects block producers**. The **token distribution among all block producers** is the basis of the random function. Your chance of being chosen rises **proportionally to your tokens relative to others**.

### Pledged, delegated and active stake

- Block producers (**Stake Pool Operators, SPOs**) try to increase their stake to improve their odds.
- **Pledge** = tokens a block producer **personally owns and contributes** to block production.
- Users who don't produce blocks can boost a producer's chance by **delegating** stake through their wallets.
- _(Source refers to "Fig. 2: Pledged and delegated stake".)_

### Live stake vs active stake

- **Live stake**: total stake a pool controls right now = operator's own stake + stake delegated by other ada holders.
- **Active stake**: live stake **as recorded in a snapshot**.
- They can differ, e.g. if delegators change their delegation after the snapshot.
- The system uses **active stake** in the rewards calculation. SPOs use active stake for block production: **higher active stake = higher chance of producing a block**.

### Liquid staking

- Stake stays **liquid** the whole time: **no locking**.
- Delegated funds can be **transferred freely**, and the associated delegation rights go with them.

---

## 2. Stake distribution snapshots

- Question: if stake is fully liquid, how do you pin down the exact stake used for the lottery? Answer: the protocol and **snapshots**.
- **Ouroboros timing:**
    - **1-second slots**; blocks filled on average **every 20 seconds**.
    - Slots grouped into **epochs of 5 days** (mainnet, currently).
    - Many mechanisms rely on epochs. **"Epoch boundary"** = the moment the system moves from one epoch to the next.
- A snapshot of the stake distribution is taken **at the start of every epoch**, reflecting the distribution from the previous epoch.
- It isn't used immediately, because the system doesn't consider it **stable** yet. Reason: **probabilistic settlement** of transactions (information is only settled after a certain period).
- **Example:** delegate in **epoch n** → included in the snapshot at the **n / n+1 boundary** → used for the slot leader schedule of **epoch n+2**.
- The system always allows **at least one entire epoch** for stake to become active.

---

## 3. Consensus rewards and the reserve

- First kind of incentive: **consensus rewards**, proportional to the **blocks produced**. Two sources:
    - **Transaction fees**: fees collected on all transactions in each block, per epoch.
    - **The reserve**: a pot of **unallocated ada** set aside at **genesis** and not yet issued.
- _Some outliers exist that aren't part of circulating supply (detailed in the report)._
- Each epoch the system puts a percentage of the reserve into circulation via rewards = the **monetary expansion, ρ (rho)**.
    - Configurable protocol parameter, **currently 0.3%**.
    - Each epoch, **at most 0.3%** of unallocated ada is released. The reserve doesn't replenish, so this amount **gradually shrinks**.
    - At this rate the reserve **halves roughly every five years**.
- **Proportional to block production:** the exact amount released depends on blocks actually produced. If only half the expected blocks are produced, only half of the planned expansion is released.
- _The source adds a slightly garbled line: under current ledger rules, if ρ became very small, the reserve could grow and the fee pot could make up the majority of the total rewards pot. Worth checking against the original._

---

## 4. Stake rewards and pool parameters

- Delegators are incentivized too: they receive a **proportion of the pool's rewards**, based on parameters set by both the protocol and the pool.
- **Fixed cost:** a flat cost is taken from the pool's total rewards. The protocol sets a minimum, the **min pool cost**, currently **170 ada**, to cover the cost of running a pool.
- **Margin (variable cost):** a percentage set by the pool. Most pools sit between **1% and 3%**.
- After costs are deducted, the remainder is split across all delegators **proportionally to the stake they contributed**.

### Pledge (parameter)

- A **minimum amount of stake the owners commit to their own pool**, as proof of seriousness. **Optional**, but a gesture of **"skin in the game"**.
- A high pledge means the pool is more likely to produce blocks (and rewards) even without many delegators yet.
- Pools **declare pledge at registration** and must **meet it through delegation**.
- **If a pool fails to meet its declared pledge, it receives no rewards at all.**

### Competing for delegators

- Not an exact science. Besides marketing and branding, parameters help pools compete: **higher pledge or lower margin** usually attract delegators.
- With incentives for pools and delegators plus liquid staking, Cardano keeps a **high share of total stake** in consensus at all times, which helps secure the network against bad actors.

---

## 5. Rewards provenance (where rewards come from and how they're split)

- The system **doesn't pay fees and block rewards directly to block producers**. They go into a **temporary reward pot**. Every block over a fixed period contributes.
- At the end of the period, a portion goes to the **Cardano treasury** (a special reserve of tokens funding ecosystem development).
- The rest is divided among block producers and delegators **in proportion to blocks minted** in that period. Pools are identified because producers **include their identifiers in blocks**.
- Pools are then assigned rewards for themselves based on **performance and chosen parameters**. The remainder goes proportionally to all other delegators.

### The reward formula (high level)

- A producer gets a portion of the total pot **R** from a complex formula. R has two components:
    1. **All transaction fees** in the block (like PoW).
    2. **Monetary expansion**, calculated periodically as extra rewards for block producers.
- The formula uses **pledged tokens**, **delegated tokens**, and two parameters set by the consensus algorithm:
    - **a0: Pledge Influence Factor**
    - **k: Stake Pool Saturation** parameter (ideal number of pools)

### k and saturation

- **k** = the **ideal number of stake pools**. **1/k** = the fraction of the maximum stake considered for one pool.
- Hence **1/k is the saturation point**: no benefit to accumulating more stake past it, since it doesn't raise rewards.
- A pool past that limit is **saturated**. Delegators then likely earn less: rewards don't grow but get split across more delegators.
- This stops pools getting too big, which would endanger **decentralisation and security**.

### a0 and multi-pool operators

- Saturation alone isn't enough: **one actor can run several pools**.
- **a0** encourages operators to **raise pledge instead of splitting it across pools**, by giving **more rewards to high-pledge pools**. A third incentive limiting centralization.
- **a0 and k are updatable protocol parameters**, so they can be tuned.

---

## 6. Rewards delay

- Because stake only becomes active in the following epoch, rewards are delayed too. They also depend on the pool's **performance in the epoch**.
- To avoid overloading the node at each epoch boundary, the system **spreads the rewards calculation across the entire following epoch**.
- Gist: stake becomes active after a delay, then starts earning after that delay. It's a **repeating cycle**, accruing rewards every epoch.
- Cardano.org hosts a **staking calculator** to estimate potential rewards from the various parameters.

---

## 7. Treasury

- A **protocol-level tax** to build a self-sustaining ecosystem and fund its development.
- The cut is a fixed percentage and another protocol parameter: **τ (tau), currently 20%**.
- Each epoch the treasury gets more ada, which can fund network activities or projects benefiting the ecosystem.
- **Collectively deciding how to use the funds** is the main focus of the **Voltaire** phase and a pillar of on-chain governance.
- **Before the Conway era:** only the **genesis entities** (by quorum) could move treasury funds. They periodically did so through **Project Catalyst**, an innovation fund promoting innovation in the ecosystem _(the source describes it as "working on a side-chain")_.
- **Conway era:** treasury management and other governance topics become the responsibility of **every ada holder, including SPOs**.
    - Outlined in **CIP-1694**, a significant step toward full on-chain governance.
    - The **updated Constitution was ratified on-chain in early 2025**.

---

## 8. The open source rewards calculation (Cardano Foundation)

### What and why

- Ouroboros rewards delegators and SPOs for securing the network. The **Cardano ledger specifications** contain the formulas.
- The CF open-sourced a **node-independent reward calculation**:
    - a way to perform and validate the rewards calculation **independent of a single implementation**
    - **comprehensive documentation** on the treasury, reserves and pool rewards
    - complemented by a white paper, **"Cardano Economic Parameters"**, published by the CF with **Professor Massimo Morini**
- **MIT-licensed** open source repository. Deepens the CF's commitment to **open source maturity** and aims to attract contributions from the wider ecosystem.
- Can also be an **educational tool** showing how protocol parameter changes could affect fund flows. Improves transparency and operational resilience.

### Why it's hard: snapshots and liquid stake

- Staked ada stays in user wallets and can be transferred any time. That's a benefit but complicates rewards calculation, hence the **snapshots** required by the ledger spec.
- **Process:**
    1. Calculate new **reserves, fees, total rewards pot and treasury**.
    2. Determine **pool rewards** from the total rewards pot.
    3. Use pool rewards to calculate **delegator and SPO rewards**.
- Because of snapshots, a stake account might become **unregistered after the snapshot** and then can't receive rewards, so **custom rules** handle those cases.
- Those rules are **spread across the codebase** because the calculation itself is distributed over time:
    - **cardano-ledger** repo holds most business logic and docs
    - some components are in **cardano-node** or the **ouroboros-network** repo
- Code runs on a **slot-based scheduler** (a slot = 1 second), which is hard to follow for newcomers. Performance optimizations make it less readable still. The open source calc aims to fix this while keeping the network's robust features.

### How the calculation flows (per the ledger spec)

- Multiple equations define the **flow of ada at the end of each epoch**.
- **Each node independently calculates** rewards per epoch in a distributed way. **No single entity does the calculation and nobody can withhold rewards.**
- Rewards come from two sources:
    - **Transaction fees**: the epoch's fee pot (sum of all fees) goes into the total rewards pot.
    - **Monetary expansion**: a fixed percentage of the reserve goes into the same pot.
- The total rewards pot is split in two: **treasury** and the **stake pool rewards pot**.
- The **reserves started at about 14 billion ada** and have gradually decreased.
- A separate calculation uses **pool parameters and apparent performance** to compute each pool's reward, which is the basis for delegator and operator rewards. All of it depends on **protocol parameters**.
- Educating people on this helps them **choose a stake pool that fits their vision and values**.

### Chimeric ledger and reward accounts

- Cardano uses a **Chimeric Ledger**: **reward accounts are separate from UTXOs** and work more like accounts in account-based chains.
- They accumulate staking rewards, avoiding lots of tiny-value UTXOs.
- Special: **can't be created arbitrarily**. Registering a staking credential **automatically creates a reward account**.

### ada-pots

- **Treasury, reserves, rewards, deposits and fees** ("ada-pots") add up to the max supply of **45 billion ada**.
- Anyone can see ada-pot numbers on explorers and **Cardano DB Sync**, but those only show **final outputs**, with no underlying data to confirm how they were computed.
- The calculations do exist in the Haskell code of the node and ledger repos, but as a **complex, highly distributed implementation** never meant as public documentation.
- **Time component:** the formula changed over time and rules changed at hard forks. E.g. getting the total rewards pot for an early epoch (**before epoch 350**) means digging back through git history of each repo.
- So the CF built a node-independent calculation that implements the ledger-spec formulas and **documents edge cases** where the spec and actual implementation differ.
- Without knowing about such "extraordinary events", it's hard to trace discrepancies between formula and treasury value, and the treasury would hold less than the formula says.

### Origin and architecture

- Originally part of **Ledger Sync**, the **Java-based data pipeline** feeding the CF's new **Cardano explorer** with chain data.
- The CF engineering team found untangling the components too complex. The diversity of input data makes gathering info from various sources time-consuming.
- Open sourcing allows **public inspection, review and verification** of the algorithm and code, and builds trust. The repo includes:
    - an **interactive chart explaining ada flow at the end of an epoch**
    - **reports highlighting differences between formula and actual value**
- Educates people about the **decentralized treasury system** and gives insight into the **use of transaction fees**. _(The source has an editor's placeholder here: "USE ICON for 'educate'". Not content.)_
- The repo is both:
    - a **testbed** for validating ledger rules and ada-pot values
    - a **Java library** used by **yaci-store** (a scoped chain indexer) to deliver rewards data **without DB Sync** (a Haskell tool that crawls node data and exposes it through a PostgreSQL database)

---

## 9. Edge cases and open questions

- Using the formula for the next epoch (e.g. to compute treasury value) sometimes **doesn't give accurate results**. Causes:
    - paying out a **Project Catalyst** proposal
    - a **MIR certificate** (**"move instantaneous rewards"**) used to compensate for pool rewards missed due to a bug
- MIR transfers are recorded transparently on-chain, but such edge cases aren't always documented in detail publicly, so there's a **lack of historical background**, which hurts transparency and leads to uncertainty and reduced trust.
- Good documentation enables future reviews and audits and strengthens credibility and operational resilience.
- **Still unknown:** early Catalyst funds and MIR certificates **before epoch 271** have **no metadata attached**.
- **Data sources:** currently a **Koios** data provider and a provider for **static JSON files** (aggregated data). A **scoped indexer**, potentially based on **Yaci-Store** (a Java-based Cardano datastore), would help maximize transparency.
- The initiative concerns the treasury (funding decentralized development), pool rewards and transaction fees, so it affects everything users care about regarding rewards. All contributors (code or information) help build trust and transparency, improving conditions for adoption.

---

## 10. Contributing, reports and findings

- The CF generates a **report with every new version** of the repo.
- Contributions aren't just code: **data, links, documentation, insights** about large differences in some epochs.
- **Test-driven** approach, so a good start is writing tests, e.g. for specific pool rewards in specific epochs.
- Reports so far cover **the treasury only**. Potential future reports: other ada-pot parts, and detailed reports on selected stake pools and member rewards.
- **Findings:**
    - The treasury value is usually about **3,500 ada higher** than the formula predicts.
    - The **pool reap rule** sends **unclaimable pool deposits** back to the treasury (e.g. a pool retires and its stake address is already deregistered).
    - Also, each pool can earn a **maximum ada value per epoch**. _(Source leaves this line brief.)_
    - A **"treasury development"** section (requested by the community) lists, per epoch, the **actual ada sent to the treasury vs the 20% it should be** (relative and absolute). It also gives the **total paid to the treasury on top of the cut, due to ledger rules: 4.2 million ada**.
- **Unit tests** ensure stability and reliability. Detailed test reports are on GitHub, and **calculation reports** (calculated vs actual values) are generated per version.
- **Future plans:** use the reports and interactive charts to **explain ada tokenomics to regulators, businesses and institutions**.
- The CF plans to keep open sourcing repos and solutions to promote Cardano's open source maturity. Open source benefits all parties, adds transparency, and improves the odds of widespread adoption.
- On GitHub you'll also find **Interesting Facts** from the research, a **Getting Started** guide and the **roadmap**. All Cardano Academy courses are backed by a glossary.

---

## Quick reference: key terms and numbers

|Term|Meaning|
|---|---|
|**Pledge**|SPO's own stake committed to their pool (optional; unmet pledge = no rewards)|
|**Live stake**|Current total stake in a pool|
|**Active stake**|Snapshot of live stake; used for rewards and block production|
|**Snapshot**|Taken at the start of each epoch; used 2 epochs later (n → n+2)|
|**Epoch**|5 days; slots are 1 second; ~1 block per 20 seconds|
|**ρ (rho)**|Monetary expansion, 0.3% of reserve per epoch (reserve halves ~every 5 years)|
|**τ (tau)**|Treasury cut, 20%|
|**a0**|Pledge influence factor|
|**k**|Ideal number of pools; 1/k = saturation point|
|**Min pool cost**|170 ada flat fee|
|**Margin**|Variable fee, typically 1% to 3%|
|**Reserve**|Unallocated ada from genesis (started at ~14 billion)|
|**Ada-pots**|Treasury + reserves + rewards + deposits + fees = 45 billion ada|
|**Chimeric ledger**|Reward accounts separate from UTXOs|
|**MIR certificate**|"Move instantaneous rewards"|
|**Pool reap rule**|Unclaimable pool deposits go to treasury|
|**Yaci-Store / DB Sync / Koios**|Chain indexer / Haskell + PostgreSQL crawler / data provider|
|**CIP-1694 / Conway era**|On-chain governance design / era where ada holders manage the treasury|