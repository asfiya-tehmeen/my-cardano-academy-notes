# Future of Digital Identity and KERI: Notes (Units 1 to 6)

## Course overview

- **Cardano Academy** course: _The Future of Digital Identity and KERI_.
- About **1.5 hours**, introductory. Aimed at **enterprise users, decision makers and developers** who want to understand the **KERI protocol**, an open standard redefining how digital identity works at its core.
- Looks at real-world implementations like **Veridian** to show the concepts in practice.
- Structure: **18 units**, each a short video of about **5 minutes**. More technical deep dives and practical courses planned.
- _These notes cover Units 1 to 6._

---

## Unit 1: The Web's Missing Identity Layer

### The problem

- The internet has a fundamental design flaw: it was built **without a native way to prove who is who**.
- Analogy: a global postal system. You can send a letter to anyone, but anyone can write "The President" as the return address. The system doesn't check, it just delivers.
- This missing layer is why **spam, phishing and impersonation** are rampant.
- ~30 years of "bolted-on" fixes, none of which fixed the root cause.

### Attempt 1: Administrative Trust ("Doorman" model)

- Basis: **Public Key Infrastructure (PKI)**, the system behind the little lock icon in your browser.
- Analogy: a bar. You trust the people inside because a **doorman (the Certificate Authority)** checked IDs at the door.
- **Flaw:** if the doorman is tricked, bribed or hacked, the whole venue is compromised. CA breaches happen constantly and compromise millions of users at once.

### Attempt 2: Algorithmic Trust ("Blockchain" model)

- Basis: anchoring identity to blockchains with **Decentralized Identifiers (DIDs)**. Instead of trusting a doorman, you trust a global network of computers reaching consensus.
- Blockchains are great at what they were designed for (**asset settlement, programmable contracts, shared state**), but identity has unique requirements.
- If your ID lives on one specific chain, it's tied to **that chain's fee structure and availability**.
- With **200+ DID methods** across chains, **interoperability** became a real challenge.
- Identity needs to move freely across networks, including blockchains.

### The solution: Autonomic Trust ("Mathematical" model)

- A third option: an identity that relies on **neither a doorman nor a blockchain**.
- Foundation of **KERI (Key Event Receipt Infrastructure)**.
- Benefits of this self-governing capability:
    - **Self-certifying**: backed by a cryptographic proof you control directly.
    - **Portable**: the proof is in the maths, not on a server, so you can take your identity anywhere. Works over **Wi-Fi, Bluetooth, or a QR code printed on paper**.
    - **Low cost**: no gas fees or subscription costs to exist.

---

## Unit 2: The Promise of Self-Sovereign Identity (SSI)

### A new paradigm

- We use digital identity for everything (banking, shopping, working), but the underlying systems are crumbling. They rely on **1990s models** never designed for this complexity.
- Right now you **don't own your digital life, you rent it**: email access from Google, bank access from a big conglomerate. If they ban you, you disappear.
- **SSI** = the shift from **renting to owning**. "You should hold your own papers." Like keeping your physical driver's licence in a leather wallet, you keep digital credentials in a **digital wallet on your phone**.

### Why we hadn't done this sooner: two flawed trust models

1. **Administrative Trust (Doorman):** third parties like Certificate Authorities vouch for us, but they get hacked.
2. **Algorithmic Trust (Blockchain):** IDs anchored to specific blockchains. Decentralization was a step forward, but tying identity to a single ledger brought **portability constraints and chain-specific costs**.

### The KERI difference: "trust the maths"

- SSI needs a foundation independent of doorman and blockchain. That's KERI, enabling **Autonomic Trust**: trust that comes **from the user, not a server**.
- **Portability:** your identity lives in your own **Key Event Log (KEL)**, so you can take it anywhere. You're not stuck on Ethereum or Bitcoin.
- **Pre-Rotation:** protects against theft. Even if a hacker steals your phone, you can **recover your account without a central help desk**.

### The three pillars of SSI

1. **User control**: you're the boss; no one can delete your identity.
2. **Decentralization**: no single point of failure; if one server goes down your identity still works.
3. **Cryptographic verifiability**: trust is proven by maths. When you show a credential, the verifier checks the **digital signature, not a database**.

### Real-world impact

- **Corporate identity:** a CEO can digitally sign a million-dollar contract and the counterparty can mathematically verify it instantly, **without calling a bank**. Enabled by **Verifiable Legal Entity Identifiers (vLEIs)** (covered later).
- **Supply chain:** a pharmaceutical company can track a **vaccine shipment** from factory to hospital with a **tamper-proof digital trail** proving it stayed at the right temperature. Possible with **Authentic Chained Data Containers (ACDCs)** (future unit).

---

## Unit 3: KERI, A New Foundation for Trust

### The quest for a universal trust layer

- The internet lacks a native identity layer. Two models have been used to patch it, and **both failed to scale globally**.

### 1. Administrative Trust basis ("Doorman")

- Used by **DNS and Certificate Authorities**; relies on a trusted third party to issue IDs.
- **Flaw:** fragile. If the administrator is hacked (which happens often), **every ID they issued** is compromised.

### 2. Algorithmic Trust basis ("Blockchain")

- Used by most **DIDs**; relies on a distributed ledger.
- Limitations for identity specifically (ties your ID to one ledger's ecosystem):
    - **Portability constraints:** ID is anchored to a specific ledger; moving between chains needs **bridges or wrappers**.
    - **Cost inheritance:** your identity inherits the **fee structure** of its chain. Fine for high-value transactions, less practical for everyday identity checks.
    - **Interoperability challenge:** with 200+ DID methods the community built **"Universal Resolvers"** to bridge them, but that adds architectural complexity KERI can avoid.

### The KERI solution: Autonomic Trust

- A third paradigm: instead of trusting an administrator or a blockchain, **you trust the identifier itself**, because it is **self-certifying**.

### How an Autonomic Identifier (AID) works

- You don't look an ID up in a registry to find the owner. **The ID is the owner's cryptographic fingerprint.**
- **The maths:** the identifier is generated directly from your **public key** (or a mathematical digest of it).
- **The result:** no third party needed to verify who controls the ID. The maths proves only the holder of the matching **private key** could have created it.
- So the ID is **portable** (works anywhere) and **secure** (no one can delete it).

### Three pillars of KERI

To work securely at internet scale, KERI relies on three mechanisms:

**1. Key Event Log (KEL): the "Single Source of Truth"**

- A personal, **tamper-proof diary** of your identity. An **append-only chain of events**.
- Each new event (e.g. rotating a key) includes a **hash of the previous event**, creating an unbreakable chain. You can't change history without breaking the cryptographic links.

**2. Pre-Rotation: "the security engine"**

- In traditional systems, a hacker who steals your key can lock you out.
- KERI separates **Active Keys** (used for signing) from **Rotation Keys** (used for recovery).
- **Mechanism:** when creating an ID you **cryptographically commit to your next key** (pre-rotation) and keep that key **hidden offline**.
- **Benefit:** a hacker with your active key **can't rotate it**, since they lack the hidden rotation key. This provides **post-quantum security** and means you can always recover your identity.

**3. Witnesses and Watchers: "the safety net"**

- How do we stop a user lying about their history? A network of **Witnesses**.
- **Ambient verifiability:** witnesses are **servers that store a copy of your KEL**. They **don't control your ID**; they just confirm **when** events happened.
- **Duplicity detection:** if a malicious user tries to rewrite history (**duplicity**), witnesses and **watchers** detect the conflict immediately. The fraud becomes **mathematically provable**, destroying trust in that ID forever.

---

## Unit 4: Autonomic Identifiers (AIDs), Your Digital Bedrock

### Recap of the two flawed models

- **Administrative Trust:** trusting a central authority (e.g. a CA). Flaw: **single point of failure**.
- **Algorithmic Trust:** anchoring IDs to a blockchain. Limitation for identity: ties your identifier's **lifecycle to one network's performance characteristics and fee model**.
- We need an identifier that relies on **neither a "Middleman" nor a "Network"**: the **AID**.

### What is an AID?

- Think of it as **Digital DNA**.
- Traditional systems: your ID is just a **random number assigned by a database** (like a row ID).
- KERI: your ID is **cryptographically derived**, generated directly from your **public key**.
- **Self-managing:** you create it yourself, no permission needed.
- **Self-certifying:** no registry needed. The maths proves only the holder of the private keys could have created that specific ID.
- **Portable:** the proof is in the ID itself, so it works on any blockchain, any network, or even offline.

### Three pillars of AID security

**1. Key Event Log (KEL), "the diary"**

- A tamper-proof chain of events. Every change of keys or settings is recorded; each event is cryptographically linked to the previous one.

**2. Self-certification**

- The cryptography element. The ID is derived from the **Inception Key** (the key used to create it), so the binding is **mathematical, not administrative**.
- You verify by **checking the signature, not by calling a helpdesk**.

**3. Pre-Rotation: "the insurance policy" / "the game changer"**

- In most systems (e.g. **Bitcoin**), if someone steals your private key they **own your assets forever**.
- **Mechanism:** commit cryptographically to your next key at creation, keep it hidden offline.
- **Benefit:** if the active key is stolen, the thief can't lock you out. You use the hidden **Rotation Key** to **revoke the stolen key and regain control**.

### AIDs in practice

**1. True portability**

- AIDs aren't "Ethereum DIDs" or "Hyperledger DIDs". They're **universal**.
- KERI acts as a **"Trust Spanning Layer"**, letting identity move freely between networks and platforms.

**2. Flexible hierarchy ("chain of command")**

- AIDs are built for **organizations**, not just individuals, and support **delegation**:
    - A **root organization** (e.g. **GLEIF**, the Global Legal Entity Identifier Foundation) delegates to an **Issuer**
    - the Issuer delegates to a **Company**
    - the Company delegates to a **CEO**
- Creates a **verifiable chain of trust** that mirrors how real businesses operate (e.g. the **vLEI ecosystem**).

**3. Unprecedented recovery**

- Pre-Rotation plus a **Watcher Network** (observers who check for fraud) lets you **detect a hack instantly and recover before damage is done**. Unique to KERI.

---

## Unit 5: Veridian, Bringing KERI to the Enterprise

### The enterprise identity dilemma

- **Option A: Centralized identity** (e.g. **Active Directory**). Problem: **vendor lock-in and single points of failure**.
- **Option B: Decentralized identity (Web3).** Problem: **complexity and poor interoperability**, "a chaotic mess".
- **Veridian** solves this: a platform that brings decentralized identity to the enterprise **without the chaos**. It wraps the **KERI protocol suite (KERI, ACDC, CESR)** into a usable, scalable product for developers and businesses.

### Strategic pivot: why not standard DIDs?

- When building Veridian they had to choose between standard DIDs and KERI. Challenges with the DID ecosystem for enterprise:
    - **Interoperability:** 200+ DID methods across chains means cross-chain verification needs **complex bridging infrastructure**.
    - **Operational cost:** enterprises working across multiple partners would need to support **multiple chain backends**, a big infrastructure burden.
    - **Architectural trade-offs:** **Universal Resolvers** bridge methods but add a layer of intermediary infrastructure that KERI's design can bypass.
- They chose KERI because it's a **universal identity layer that can work alongside any blockchain, including Cardano**, rather than competing with one.
- **Analogy: KERI is "TCP/IP for Trust".** It doesn't care what network you're on; it creates a universal layer where any identity can verify any other, whatever the underlying infrastructure.

### A new foundation: Autonomic Trust

- Most identity systems use **Algorithmic Trust** (trusting a blockchain). **Veridian uses Autonomic Trust** (trusting the identifier).
- **Difference:** in KERI the identifier is self-certifying. Validity is proven by **its own cryptographic history (the KEL)**, not by checking a ledger.
- **Benefit:** portable. You can move your corporate identity **from a cloud server to a local data center without breaking it**.

### Enterprise-grade features

Veridian picked KERI because its features map directly to enterprise needs:

**1. Solving key compromise (Pre-Rotation)**

- Traditionally, a stolen corporate root key is a catastrophe; the company might have to **revoke millions of credentials**.
- With Pre-Rotation it becomes a **manageable incident**: the **Rotation Key is kept offline (cold storage)**, so a hacker with the active **Signing Key** can't take over. The company uses the cold key to lock the hacker out and restore control.

**2. Proactive security (Watcher Network)**

- Watchers = a **decentralized security team**, monitoring the identifier's history **24/7**.
- If an attacker tries to publish a fake history (**duplicity**), watchers detect it instantly, so the company can react **before customers are harmed**.

**3. Governance (Multi-Signature)**

- Real businesses don't rely on one person with one key. KERI supports **Weighted Multi-Sig**.
- Example rule: signing a **low-value invoice** needs **one key (the Manager)**; signing a **high-value contract** needs a **weight of three (CEO + COO + CFO)**.
- Lets Veridian mirror your corporate governance structure in code.

**4. Verifiable chains (ACDC)**

- ACDCs allow chains of trust. **GLEIF model:** Global Foundation → delegates to Issuer → Issuer delegates to Company → Company delegates to Employee.
- Gives a clear, **audit-proof path of authority** for every action the enterprise takes.

---

## Unit 6: ACDC, Beyond Simple Credentials

### What an ACDC is

- **Authentic Chained Data Containers (ACDCs)**: a much more powerful framework than a simple standalone credential (like a PDF course certificate).
- Defined by an **emerging IETF specification**. Moves beyond isolated attestations to **complex, verifiable data relationships**.
- A container designed to prove **exactly who authored data and where it came from**.
- Structured as **Directed Acyclic Graphs (DAGs)**: data is linked so the "arrows" only point one way. This prevents **circular logic** and ensures a clear flow of information.
- Each ACDC is a **node** connecting to other containers through cryptographically verifiable links, or **edges**, so you can build digital structures that mirror real-world hierarchies.

### Advantages over W3C Verifiable Credentials

- **Schema referencing (no link rot):**
    - Standard credentials often use **URLs** to define structure. If the site goes offline or the file moves, **the credential breaks**.
    - ACDCs use a **Content-Addressable Secure Hash**, a **Self-Addressing Identifier (SAID)** (expanded on later). Rules are **locked mathematically**, not hosted on a server, so the credential stays valid for decades.
- **Scope of use:** supports both **targeted credentials** (issued to a specific person) and **untargeted signed documents** (like a public audit report).
- **Data chaining** (the "killer feature"): ACDCs link into chains, modelling **provenance (history)** and **delegation (permission)**.

### ACDC chaining

- The power is in the **edge section**: cryptographic pointers letting one credential reference another, creating a **provable line of authority**.
- **Example:** a government authority issues an **Accreditation Credential** to a University; the University issues a **Diploma Credential** to a Student.
    - The diploma uses an edge pointing back to the University's accreditation.
    - When an employer verifies the diploma, software **crawls up the chain** and confirms the diploma is valid **and** that the university was accredited **at the time of issuance**.
- Chaining unlocks:
    - **Cryptographic provenance:** tamper-evident chain of custody, vital for supply chains.
    - **Delegated authority:** e.g. proving a manager has authority, delegated from a director, to sign a purchase order.
    - **Complex logic:** chains can include rules, e.g. "This Purchase Order is valid **only** if signed by a manager with a 'Budget Authority' credential."

### ACDC in action: the GLEIF vLEI

- Best real-world example: the **verifiable Legal Entity Identifier (vLEI)** system, which uses a chain of ACDC credentials to represent corporate authority:
    1. **GLEIF (Root):** the global root of trust.
    2. **QVI (Issuer):** a **Qualified vLEI Issuer** accredited by GLEIF.
    3. **Legal Entity:** the company itself.
    4. **OOR (Role):** an **Official Organizational Role** credential held by an individual, e.g. a CEO.
- Lets a CEO digitally sign a document and **prove mathematically** they have authority to act for the company.
- This model is now an **ISO standard (ISO 17442-3)**.

---

## Quick comparison: the three trust models

||Administrative Trust|Algorithmic Trust|Autonomic Trust|
|---|---|---|---|
|Nickname|The Doorman|The Blockchain|The Mathematical model|
|What you trust|A central authority (CA, DNS)|A distributed ledger/network|The identifier itself|
|Examples|PKI, Certificate Authorities|DIDs (200+ methods)|KERI|
|Main weakness|Single point of failure; breaches compromise every ID issued|Tied to one chain's fees, availability and ecosystem; needs bridges, Universal Resolvers|(Solution to the other two)|
|Portability|Low|Limited|High: any network, offline, QR code|

---

## Quick reference: key terms

- **PKI**: Public Key Infrastructure (browser lock icon).
- **CA**: Certificate Authority (the "doorman").
- **DID**: Decentralized Identifier.
- **KERI**: Key Event Receipt Infrastructure.
- **AID**: Autonomic Identifier, cryptographically derived from the public key ("digital DNA").
- **SSI**: Self-Sovereign Identity (own, don't rent).
- **KEL**: Key Event Log, append-only hash-chained diary of the identity.
- **Inception Key**: key used to create the AID.
- **Pre-Rotation**: committing to the next key, held offline, for recovery.
- **Active / Signing Key vs Rotation Key**: day-to-day signing vs offline recovery.
- **Witness**: server that stores a copy of the KEL and confirms when events happened.
- **Watcher**: observer that monitors for fraud/duplicity.
- **Duplicity**: attempt to rewrite or fork identity history.
- **Ambient verifiability**: verification available from anywhere via witnesses.
- **Trust Spanning Layer / TCP/IP for Trust**: KERI as a universal layer across networks.
- **Weighted Multi-Sig**: signing thresholds based on key weights.
- **ACDC**: Authentic Chained Data Containers (IETF draft).
- **DAG**: Directed Acyclic Graph.
- **Edge**: cryptographic link from one ACDC to another.
- **SAID**: Self-Addressing Identifier (content-addressable hash).
- **vLEI**: verifiable Legal Entity Identifier (ISO 17442-3).
- **GLEIF**: Global Legal Entity Identifier Foundation (root of trust).
- **QVI**: Qualified vLEI Issuer.
- **OOR**: Official Organizational Role credential.
- **Veridian**: enterprise platform wrapping KERI, ACDC and CESR.
- **CESR**: part of the KERI protocol suite (named, not explained, in these units).