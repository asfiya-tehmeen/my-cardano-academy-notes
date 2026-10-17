# Benefits, Decision Frameworks and Use Cases

The rest of the course focuses on the business side: the types of use cases blockchain enables and some of the business models that have come out of it. The aim is that by the end you can decide whether blockchain is the right fit for your business.

---

## 1. Benefits of blockchain for business

- **Transaction times**
    - Compared with traditional inter-bank transfers, Cardano has shown it can send **thousands of digital assets to multiple recipients globally, settled in minutes, for minimal fees**.
    - No verification needed from a central authority or clearing house.
- **Cost savings**
    - Network is **self-policed** by participants through "inclusive accountability".
    - **"Killing the middleman"**: no intermediaries, participants exchange value directly.
    - **No duplicated effort**, because the shared ledger is a single source of truth.
- **Security**: blockchain inherently protects against interference, fraud and hacking.
- **Privacy**
    - The **Cardano Foundation** offers a **digital identity wallet** prioritizing security, privacy and interoperability, to drive adoption and support existing ecosystems.
    - Users can securely generate, update, deactivate and restore **Decentralized Identifiers (DIDs)** and **KERI Autonomic Identifiers (AIDs)** (KERI = Key Event Receipt Infrastructure).
    - **Zero knowledge proofs** and other cryptographic primitives allow **selective disclosure** and other advanced privacy features.
- **Auditability**: a shared public ledger gives a **"single pane of glass"** for monitoring and auditing transactions.
- **Operational efficiency**
    - Cryptocurrencies and their blockchains run **24/7**, with no "business days" or public holidays.
    - **Tokenization** of assets allows near-instant transfer of ownership.
- **Smart contracts for business terms and conditions**: can be written to be **self-executing and self-enforcing**, which is more secure and efficient than paper contracts.

### Permissioned vs permissionless

- Blockchains can be either.
- Some companies use **permissioned** blockchains for privacy. Each participant gets a **unique identity**, so policies can restrict participation and access to sensitive details.
- Sometimes adopted out of necessity to meet data protection rules, e.g. protecting medical records under **HIPAA** (Health Insurance Portability and Accountability Act).

---

## 2. Is blockchain right for your business?

### Starter questions

1. **Once-off or ongoing, repeatable process?** Can it be fully automated? If only partly, is it worth pursuing?
2. **How many stakeholders?** Do they all need to be honest? E.g. is a **5-of-7 multi-signature** enough for consensus? What's the threshold?
3. **Multiple disparate data sources?** Blockchain can help consolidate different data types and keep data consistent.
4. **Is there a value transfer?** Can an old process be streamlined with blockchain?
5. **Need for immutability** and permanent records?
6. **Need for reliable performance?** E.g. Cardano fees are **deterministic**: you can predict them accurately in advance, and the same transaction won't cost different amounts at different times.
7. **What's the right strategy: blue ocean or red ocean?**
    - Cardano executed a **blue ocean** strategy.
    - A **red ocean** strategy would have meant forking Bitcoin or Ethereum and competing head-on as a PoW chain.
    - Cardano's blue ocean approach: first-principles, academic research-based. Much of it is custom built, with many industry firsts:
        - first provably secure PoS consensus protocol (**Ouroboros**)
        - first **liquid, non-custodial staking** model
        - first **eUTXO accounting model at scale**
8. **What industry are you in?** Is **ESG** (Environmental, Social and Corporate Governance) a requirement or a nice-to-have?
9. **Have you catered for blockchain's drawbacks?**

### Drawbacks to be aware of

- Blockchain isn't always a silver bullet.
- **Immutability** can be frustrating when you need to correct earlier work.
- Assets are secured with **public key cryptography**. **Lose your seed phrase and you could lose all your funds.**
- A **10-minute settlement time** isn't great if you're selling ice cream on a hot day with a long queue.
- There are workarounds and best practices, but know about the hiccups.

### Frameworks for assessing your idea

- Best to use a **mix** of frameworks.
- **Porter's Five Forces**: five key sources of competitive pressure in an industry. Useful for weighing up your new product's competitiveness:
    1. threat of new entrants
    2. bargaining power of buyers
    3. bargaining power of suppliers
    4. threat of new substitutes
    5. competitive rivalry
- **SWOT analysis**: Strengths, Weaknesses, Opportunities, Threats.
- **Gartner Hype Cycle**: graphic of a technology's maturity and adoption. Good for an emerging technology like blockchain. Where Cardano sits on it is subjective and people read the chart differently, but it can help show where real business value and opportunity are.
- **Price and market cycles:**
    - Many people hate focusing on price alone, but many blockchains are **intrinsically tied to their native currency**.
    - Crypto market cycles can't be ignored. **Many businesses die each bear market** because they underestimate the swings.
    - The famous **"Wall Street Cheat Sheet"** helps traders understand and navigate market movements. It shows the psychological side of trading, which is relatable for anyone working in the industry.
- These are just a sample of the tools available.

---

## 3. Use cases overview

- Use cases are "only limited by your imagination".
- **Deloitte and McKinsey** research suggests blockchain has use cases across **all verticals**.
- **Gartner** predicts blockchain's business value will grow to **$176 billion by 2025** and **$3.1 trillion by 2030**.

### Common characteristics of use cases

- **Digital scarcity**
    - Digital assets can have fixed or variable supply.
    - Native currencies like bitcoin and ada have **deflationary models** with rewards decreasing over time.
    - Much of the NFT craze is fuelled by speculation on the scarcity of tokenized assets.
- **Payment rails**: secure, efficient transfer of value.
    - Legacy remittance infrastructure is outdated, expensive and opaque.
    - Migrants sending money to developing countries are charged **extortionate rates**.
    - **Credit card transactions can take up to 7 business days** to settle behind the scenes.
    - Blockchain is faster, cheaper and transparent.
    - Cardano's eUTXO model lets **thousands of digital assets** go to multiple recipients in one transaction. See **eutxo.org** to watch blocks being minted live.
- **Distributed ledger (DLT)**
    - Lets anyone track the **origin, ownership, production process, transportation and storage** of tokenized physical assets and digital assets.
    - All without a central authority.

---

## 4. Web3

### Web 1.0, 2.0, 3.0

|Stage|Era|Description|
|---|---|---|
|**Web 1.0**|1990s|Static, text-based sites. Users mainly **"read"**. Like an encyclopaedia: you could search and study, but little interactivity.|
|**Web 2.0**|1999 (term coined by **Darcy DiNucci** to distinguish from 1.0)|Interactive sites like YouTube and Facebook. Users **"read" and "write"**. Big tech subsidised the huge storage costs so users could upload content, and social media was born. User content brought reactions, and "sentiment"-based algorithms grew ever more sophisticated.|
|**Web3**|Term introduced by **Gavin Wood** (Ethereum co-founder)|Next iteration of the internet, built around blockchain. A decentralized network where users **"read", "write" and "own"** their content, currency and digital assets.|

- Web3 is somewhat of a buzzword, but the idea: blockchain "kills the middleman", and here the middlemen are **big tech companies**, whose stranglehold on user data gets removed.

### Examples and related ideas

- **Brave browser** (based on Google Chromium): protects privacy using blockchain.
    - Most people unwittingly give away lots of data just by browsing.
    - Brave flips the ad model by compensating for ads in its **ERC-20 token, BAT (Basic Attention Token)**.
- **Semantic web**: computers can comprehend and use information as humans do.
- **Content authenticity vs deep fakes:**
    - With AI advancing so fast, blockchain may be adopted out of necessity to ensure the integrity of digital content.
    - Possibly the biggest future use case: **verifying and authenticating digital content**.
    - Example: a video's unique **hash** recorded on-chain. Before playing, cross-check its hash against the on-chain one.
- **Infrastructure alternatives to big cloud providers** (less glamorous):
    - **IPFS (Interplanetary File System)**: like a file system for the blockchain world. Store and retrieve large data sets with blockchain benefits (decentralisation, data integrity, etc.).
    - Also **decentralised compute** offerings.

---

## 5. DeFi (Decentralized Finance)

- Arguably the **number one blockchain use case to date**.
- **TradFi** has barriers to entry and can discriminate against the developing world. **DeFi** is more inclusive: no **KYC**, registration or minimum balances.
- Open, transparent, decentralized alternative by removing intermediaries.
- Users **self-custody** their assets and transact directly with anyone globally.

### History

- "DeFi" was coined in **2018** by Ethereum developers who introduced smart contracts to blockchain, building on Bitcoin's **2009** breakthrough as the first peer-to-peer digital currency.
- **ERC token standards** opened the door to NFTs and financial services such as:
    - stablecoins
    - decentralized exchanges
    - lending and borrowing protocols
    - **yield farming**: depositing tokens into a **liquidity pool** to earn rewards, paid in a native currency or sometimes the protocol's own token. Think of it as providing liquidity in return for favourable interest rates.

### Growth and risks

- DeFi has grown steadily as other chains add to **total value locked (TVL)**, tracked on sites like **DefiLlama** _(the source spells it "DefiLama")_.
- Unregulated industry = plenty of scams. **DYOR** (do your own research).

### CEX vs DEX

- Newcomers often leave funds on **centralized exchanges (CEXs)** for convenience, but it's generally **safer to self-custody**: total control and access.
- DeFi mostly happens on **decentralized exchanges (DEXs)**: trading through **self-executing smart contracts** and peer-to-peer transactions. No intermediaries; ada and digital assets move between users' wallets.
- **DEXs on Cardano** use the **determinism (reliability)** of the eUTXO model.

### Stablecoins

- A **fixed-price cryptocurrency**, pegged to or backed by another stable asset.
- Enable instant payment and settlement, and most importantly a **safe haven from volatility**.
- Represent a stable asset however other assets move, or if a country has high inflation and an unstable currency.
- Generally accepted as essential for a blockchain's DeFi ecosystem to thrive.
- _Different kinds covered in future courses._

---

## 6. Tokenization and tokens

### Tokenization

- **Tokenization** = on-chain digital representation of real-world assets.
- On Cardano, **native assets (tokens)** are the smallest pieces of data on the chain, defined by **three things: a name, a minting policy, and an amount**.

### Example: diamonds

- "Blood diamonds" are mined in war zones and sold to fund nefarious activity.
- The **Kimberley Process (2003)** is a multilateral trade regime with safeguards to keep blood diamonds out of the global supply chain, including criteria to certify legitimate sources.
- Blockchain is an obvious fit: an **immutable audit trail** supports compliance and lets retailers verify suppliers' credentials.
- **NMKR** (an NFT and tokenization service) partnered with **Tiamonds** to bring **tokenized diamonds to Cardano** and offer user-friendly plug-and-play tools for projects.

### Uses of fungible tokens

- **DeFi DAO tokens**: e.g. a utility token integral to a decentralized lending/borrowing protocol. With a non-custodial system, **NFT-backed loans** are possible, letting users leverage their digital assets.
- **Loyalty points** to reward and incentivize readers.
- **Wrapped assets**: e.g. **Wrapped BTC** is a synthetic version of Bitcoin, represented by a token built and deployed through a smart contract on other blockchains.
- **Meme coins**: tokens usually based on a joke rather than real-world utility.
- **Staking**: native tokens can be staked to take part in a protocol's operation. Users benefit from **yield farming**: staking **Liquidity Provider (LP) tokens** to earn extra rewards, usually in the platform's native token.

### Uses of NFTs

- Profile pictures
- Digital art
- Collectibles
- **Digital twins**: a digital copy of something in the real world
- **POAPs (Proof of Attendance Protocol)**: show you attended or took part in an event
- **Fractional ownership** of physical assets like property and fine art
- **Gaming** (next section)

---

## 7. Gaming and the metaverse

- Trillions of US dollars were printed in **2020** alone, while many cryptos (bitcoin, ada) have a **hard supply cap**, creating scarcity. That scarcity extends to tokens and digital assets in gaming and the metaverse.
- **Metaverse** = a 3D virtual world built on augmented and virtual reality, popular for online role-playing games.
- **McKinsey & Company** predicts the metaverse economy will reach **$5 trillion by 2030**.
- Markets form around creating and trading tokens/digital assets. E.g. gamers get in-game assets for clearing stages. These can be tokens, collectibles, virtual land, NFTs, art, avatars etc., with varying digital scarcity.
- **GameFi** (Game Finance): many games popular with **"play to earn"** models. Players earn digital assets by hitting milestones, beating real players, or beating AI opponents. Assets can often be traded on real-world exchanges.
- **Pay to play (Web 2.0 games):** often subscription-based. The gamer is just paying for a **licence that the studio can take away**, with no incentive around earning, collecting or trading assets.
- Blockchain gives gamers **true ownership**.
- Web2 games currently handle more transactions and active players than Web3 games, but the gap is closing as scaling solutions mature.

---

## 8. Payment rails

- A **payment rail** = digital infrastructure enabling money transfers.
- **TradFi** = centralised institutions controlling the flow of funds between permissioned parties, in exchange for fees. Fees are usually high compared with blockchain, mostly due to the lack of credible remittance alternatives.
- On a blockchain, counterparties transfer value on a **public ledger** that records and validates details publicly, at the same time, for everyone.
- Blockchain disrupts the hierarchical financial system by **"killing the middleman"**. The middlemen include:
    - **RTGS** (real-time gross settlement) networks or equivalents
    - **Interbank networks**: **CHIPS** (Clearing House Interbank Payments System), **ACH** (automated clearing house), **Fedwire**, and others
    - **SWIFT** (Society for Worldwide Interbank Financial Telecommunications): the communication network for ACH and wire transfers
    - **Credit card networks**: Visa, MasterCard, American Express. _Visa is now enabling crypto withdrawals at large scale._
    - **Fintech apps**: Stripe, PayPal, Revolut etc., which connect to ACH or RTGS to settle payments. They now also let users buy, hold and sell crypto.
- **Irreversibility:** blockchain transactions are irreversible, but **custom logic in smart contracts** can allow some recourse for disputes, failure to deliver a service, or other breaches of trust.
- Blockchains are **permissionless** and inclusive for anyone with an internet connection.

---

## 9. Supply chains and traceability

- Supply chains often involve many intermediaries consolidating many data sources to track goods from supplier to consumer.
- Blockchain simplifies interactions between stakeholders: every touch-point can be tracked and logged on a shared public ledger.
- **Shipping:** international shippers use blockchain to monitor shipments and make sure containers aren't tampered with.
- **Perishables:** businesses can review the whole path on-chain. **Payment can be made on confirmed delivery**, when a smart contract triggers the transfer.
- **Benefits for everyone:**
    - more transparency makes auditors' lives easier
    - adverse conditions or mistreatment (intentional or not) can be identified and mitigated
    - in the developing world, fewer intermediaries to pay (financial inclusion)
- Replicable wherever **transparency and traceability** are needed.

### Real examples

- **Georgian wine:** the **Cardano Foundation**, with **Georgia's National Wine Agency**, the **Bolnisi Winemakers Association** and **Scantrust**, built a solution on Cardano to ensure the **quality and authenticity** of Georgian wine.
- **Dubai Police:** **Mohammad AlShamsi** (Head of Firearms and Toolmarks Section) explained at the **Cardano Summit 2023** how blockchain helps combat organized crime through shared, transparent data for **tracing firearms across borders**.

---

## 10. Healthcare

- Any process with **disparate data sources** can benefit. Healthcare is an obvious candidate: digital health records can be stored and shared with strong security.
- Advances in **Zero Knowledge** and **private smart contracts** mean healthcare data systems could shield confidential information while still allowing **selective disclosure** when needed.
- Hospitals today usually have information **siloed across different data systems**.
- With blockchain plus **DIDs**, patients and providers can **control what they share and with whom**.

---

## 11. ESG (Environmental, Social and Governance)

- Many businesses now have an ESG mandate. Putting ESG data on blockchain lets them show **trust, accuracy and regulatory compliance**. Because blockchain is decentralized, ESG reporting is more **reliable and verifiable**.
- **Proof of ESG**: a business using blockchain to verify ESG data. Once ESG data is recorded it **can't be tampered with**, which ensures integrity. This transparency and trust is missing from traditional ESG reporting.
- **Veritree**: the **Cardano Foundation** partnered with them. World's first fully integrated platform for **tree restoration through blockchain**.
- **Sustainable Ada**: a project that compiled the **Cardano Impact Report 2023**, describing how blockchain is recalibrating how we view value, identity, and positive social and environmental impact.

---

## Wrap-up

- The course only scratches the surface of what's possible on blockchain.

---

## Quick reference: key terms

- **Permissioned / permissionless**: restricted participation with identities / open to anyone.
- **HIPAA**: US health data protection law.
- **DID / AID / KERI**: decentralized identifiers / autonomic identifiers / Key Event Receipt Infrastructure.
- **Blue vs red ocean**: new uncontested market vs competing head-on in an existing one.
- **Porter's Five Forces**: new entrants, buyer power, supplier power, substitutes, rivalry.
- **SWOT**: Strengths, Weaknesses, Opportunities, Threats.
- **Gartner Hype Cycle**: maturity/adoption curve of a technology.
- **Payment rail**: infrastructure for moving money.
- **DLT**: distributed ledger technology.
- **Web 1.0 / 2.0 / 3.0**: read / read-write / read-write-own.
- **BAT**: Basic Attention Token (Brave, ERC-20).
- **IPFS**: Interplanetary File System.
- **DeFi / TradFi**: decentralized / traditional finance.
- **TVL**: total value locked.
- **DYOR**: do your own research.
- **CEX / DEX**: centralized / decentralized exchange.
- **Yield farming**: depositing tokens in a liquidity pool for rewards.
- **LP token**: Liquidity Provider token.
- **Stablecoin**: pegged, fixed-price crypto.
- **Wrapped asset**: token version of an asset on another chain (e.g. Wrapped BTC).
- **POAP**: Proof of Attendance Protocol.
- **Digital twin**: digital copy of a real-world item.
- **GameFi / play to earn**: gaming with earnable, tradable digital assets.
- **Metaverse**: 3D virtual world on AR/VR.
- **RTGS / CHIPS / ACH / Fedwire / SWIFT**: traditional payment and messaging networks.
- **ESG**: Environmental, Social and Governance.
- **Kimberley Process**: 2003 trade regime against blood diamonds.