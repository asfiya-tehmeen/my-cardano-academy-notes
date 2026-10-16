# The Web’s Missing Identity Layer

Welcome to the Cardano Academy’s course on the Future of Digital Identity and KERI. This is an hour and half long introductory course designed for enterprise users, decision makers and developers who want to understand the KERI protocol…the open standard redefining how digital identity works at its core…

Along the way, we'll look at real-world implementations like Veridian to see how these concepts are being put into practice today.

Let’s get started with our first unit which is all about the web’s missing identity layer.

The course is structured into 18 units, each corresponding to a short video of approximately 5 minutes. More technical deep dives and practical courses are planned in future.

The internet has a fundamental design flaw: it was built without a native way to prove who is who. Think of it like a global postal system. You can send a letter to anyone, but anyone can write "The President" on the return address. The system doesn't check; it just delivers the mail.

This missing layer is why spam, phishing, and impersonation attacks are rampant. We have spent 30 years trying to patch this hole with "bolted-on" solutions, but none have truly fixed the root cause.

## Attempt 1: Administrative Trust (The "Doorman" Model)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%201_%20The%20Web%E2%80%99s%20Missing%20Identity%20Layer.md#attempt-1-administrative-trust-the-doorman-model)

The first attempt to fix this was Public Key Infrastructure (PKI)—the system behind the little lock icon in your browser. We call this Administrative Trust. Think of it like a bar. You trust that people inside are safe because a doorman (the Certificate Authority) checked their IDs at the door.

The flaw is if the doorman is tricked, bribed, or hacked, the whole venue is compromised. We see this constantly when Certificate Authorities get breached, compromising millions of users at once.

## Attempt 2: Algorithmic Trust (The"Blockchain” Model)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%201_%20The%20Web%E2%80%99s%20Missing%20Identity%20Layer.md#attempt-2-algorithmic-trust-theblockchain-model)

Next, we tried anchoring identity directly to blockchains using Decentralized Identifiers (DIDs). We call this Algorithmic Trust. Instead of trusting a doorman, we trust a global network of computers to reach consensus.

Blockchains are phenomenal at what they were designed for — asset settlement, programmable contracts, and shared state. But identity has unique requirements. If your ID lives on one specific blockchain, your identity becomes tied to that chain’s fee structure and availability. With over 200 different DID methods emerging across different chains, interoperability became a real challenge. Identity needs to move freely across networks — including blockchains.

## The Solution: Autonomic Trust (The "Mathematical" Model)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%201_%20The%20Web%E2%80%99s%20Missing%20Identity%20Layer.md#the-solution-autonomic-trust-the-mathematical-model)

We need a third option. An identity that doesn't rely on a doorman or a blockchain. We call this Autonomic Trust. This is the foundation of Key Event Receipt Infrastructure, aka KERI. With this self-governing capability, we enjoy several benefits:

It’s Self-Certifying, so your identity is backed by a cryptographic proof that you control directly. It’s Portable. Because the proof is in the maths, not on a server, you can take your identity anywhere. It works over Wi-Fi, Bluetooth, or even a QR code printed on paper. It’s Low Cost. You don't need to pay gas fees or subscription costs to exist.

# The Promise of Self-Sovereign Identity (SSI)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%202%3A%20The%20Promise%20of%20Self-Sovereign%20Identity%20\(SSI\).md#the-promise-of-self-sovereign-identity-ssi)

## A New Paradigm

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%202%3A%20The%20Promise%20of%20Self-Sovereign%20Identity%20\(SSI\).md#a-new-paradigm)

We use digital identity for everything—banking, shopping, working. But the systems underneath are crumbling. We rely on models from the 1990s that were never designed for this level of complexity. Currently, you don't own your digital life; you rent it. You "rent" your email access from Google. You "rent" your bank access, likely from one of the big conglomerates. If they ban you, you disappear.

Self-Sovereign Identity (SSI) is the shift from renting to owning. It is a simple idea: You should hold your own papers. Just as you keep your physical driver's license in your leather wallet, you should keep your digital credentials in a digital wallet on your phone.

## The Flaws of Current Models

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%202%3A%20The%20Promise%20of%20Self-Sovereign%20Identity%20\(SSI\).md#the-flaws-of-current-models)

Why haven't we done this sooner? Because we were stuck with two flawed trust models:

1. Administrative Trust (The Doorman model, on-screen but not spoken): We trusted third parties like Certificate Authorities to vouch for us. But they get hacked.
2. Algorithmic Trust (The blockchain model, on-screen but not spoken): We anchored IDs to specific blockchains. While the decentralization was a step forward, tying identity to a single ledger introduced portability constraints and chain-specific costs.

## The KERI Difference: Trust the Maths

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%202%3A%20The%20Promise%20of%20Self-Sovereign%20Identity%20\(SSI\).md#the-keri-difference-trust-the-maths)

To make SSI actually work, we need a foundation that doesn't depend on a doorman or a blockchain. That foundation is KERI. KERI allows for Autonomic Trust—trust that comes from the user, not a server.

Portability: Because your identity lives in your own Key Event Log (KEL), you can take it anywhere. You aren't stuck on the Ethereum network or the Bitcoin network. Pre-Rotation: KERI protects you from theft. Even if a hacker steals your phone, KERI's "Pre-Rotation" feature allows you to recover your account without asking a central help desk.

## The Three Pillars of SSI

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%202%3A%20The%20Promise%20of%20Self-Sovereign%20Identity%20\(SSI\).md#the-three-pillars-of-ssi)

1. User Control: You are the boss. No one can delete your identity.
2. Decentralization: No single point of failure. If one server goes down, your identity still works.
3. Cryptographic Verifiability: Trust is proven by maths. When you show a credential, the verifier checks the digital signature, not a database.

## Real World Impact

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%202%3A%20The%20Promise%20of%20Self-Sovereign%20Identity%20\(SSI\).md#real-world-impact)

This technology solves massive real-world problems:

- Corporate Identity: A CEO can digitally sign a million-dollar contract, and the counterparty can mathematically verify it is valid instantly, without calling a bank. This is enabled with Verifiable Legal Entity Identifiers, vLEIs, which we will talk about later.
- Supply Chain: A pharmaceutical company can track a vaccine shipment from the factory to the hospital, with a tamper-proof digital trail proving it was kept at the right temperature. This is possible with Authentic Chained Data Containers, ACDCs…the focus of a future unit.


# KERI - A New Foundation for Trust

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#keri---a-new-foundation-for-trust)

## The Quest for a Universal Trust Layer

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#the-quest-for-a-universal-trust-layer)

We have established that the internet lacks a native identity layer. To date, we have tried to patch this flaw with two main models, but both have failed to scale globally.

## 1. The Administrative Trust Basis (The "Doorman")

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#1-the-administrative-trust-basis-the-doorman)

Used by DNS and Certificate Authorities, this relies on a trusted third party to issue IDs.

The flaw is that it’s fragile. If the Administrator is hacked, which happens frequently, the integrity of every ID they issued is compromised.

## 2. The Algorithmic Trust Basis (The "Blockchain")

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#2-the-algorithmic-trust-basis-the-blockchain)

Used by most Decentralized Identifiers (DIDs), this relies on a distributed ledger.

The limitation for identity specifically is that it ties your ID to one ledger's ecosystem:

- Portability Constraints: Your ID is anchored to a specific ledger. Moving between chains requires bridges or wrappers.
- Cost Inheritance: Your identity inherits the fee structure of whichever chain it lives on — fine for high-value transactions, less practical for everyday identity checks.
- The Interoperability Challenge: With 200+ DID methods, the community built "Universal Resolvers" to bridge them — but this adds architectural complexity that KERI can avoid."

## The KERI Solution: Autonomic Trust

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#the-keri-solution-autonomic-trust)

KERI introduces a third paradigm: Autonomic Trust. Instead of trusting an administrator or a blockchain, you trust the Identifier itself. This is possible because the Identifier is Self-Certifying.

## How an Autonomic Identifier (AID) Works

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#how-an-autonomic-identifier-aid-works)

In KERI, we don't look up an ID in a registry to find the owner. The ID is the owner's cryptographic fingerprint.

- The Maths: The Identifier is generated directly from your Public Key (or a mathematical digest of it).
- The Result: You don't need a third party to verify who controls the ID. The maths proves that only the person holding the corresponding Private Key could have created it. This makes the ID Portable, in that it works anywhere, and Secure… no one can delete it.

## The Pillars of KERI

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#the-pillars-of-keri)

To make this work securely at internet scale, KERI relies on three mechanisms:

## 1. The Key Event Log (KEL)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#1-the-key-event-log-kel)

The KEL is the "Single Source of Truth." It is a personal, tamper-proof diary of your identity. It is an append-only chain of events. Each new event, like rotating a key, includes a hash of the previous event. This creates an unbreakable chain—you cannot change your history without breaking the cryptographic links.

## 2. Pre-Rotation (The Security Engine)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#2-pre-rotation-the-security-engine)

In traditional systems, if a hacker steals your key, they can lock you out. KERI solves this by separating Active Keys (used for signing) from Rotation Keys (used for recovery).

- The Mechanism: When you create an ID, you cryptographically commit to your next key (Pre-Rotation), but you keep that key hidden offline.
- The Benefit: Even if a hacker steals your active key, they cannot rotate it, because they don't have the hidden Rotation Key. This provides Post-Quantum Security and ensures you can always recover your identity.

## 3. Witnesses and Watchers (The Safety Net)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%203%3A%20KERI%20-%20A%20New%20Foundation%20for%20Trust.md#3-witnesses-and-watchers-the-safety-net)

How do we ensure a user doesn't lie about their history? We use a network of Witnesses.

- Ambient Verifiability: Witnesses are servers that store a copy of your KEL. They don't control your ID; they just confirm when events happened.
- Duplicity Detection: If a malicious user tries to rewrite history (Duplicity), the Witnesses and Watchers detect the conflict immediately. The fraud becomes mathematically provable, destroying the trust in that ID forever.


## The Quest for a Better ID

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#the-quest-for-a-better-id)

We have established that the internet lacks a native trust layer. To date, we have relied on two flawed models:

- Administrative Trust: Trusting a central authority (like a Certificate Authority) to issue IDs. Flaw: Single point of failure.
- Algorithmic Trust: Anchoring IDs to a blockchain. Limitation for identity: ties your identifier's lifecycle to a single network's performance characteristics and fee model.

These limitations highlight the urgent need for a new foundation. We need an identifier that doesn't rely on a "Middleman" or a "Network." We need The Autonomic Identifier (AID).

What is an AID? Think of an AID as Digital DNA. In traditional systems, your ID is just a random number assigned to you by a database (like a Row ID). In KERI, your ID is Cryptographically Derived. It is generated directly from your Public Key.

- Self-Managing: You create it yourself. You don't ask permission.
- Self-Certifying: You don't need a registry to prove it's yours. The maths proves that only the person holding the private keys could have created this specific ID.
- Portable: Because the proof is in the ID itself, you can use it anywhere—on any blockchain, any network, or even offline.

## The Three Pillars of AID Security

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#the-three-pillars-of-aid-security)

How do we make this secure without a central bank or blockchain? We rely on three pillars:

## 1. The Key Event Log (KEL)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#1-the-key-event-log-kel)

The KEL is the Diary of your identity. It is a tamper-proof chain of events. Every time you change your keys or settings, it is recorded here. Each event is cryptographically linked to the previous one, creating an unbreakable chain of history.

## 2. Self-Certification

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#2-self-certification)

This is the cryptography element. Because the ID is derived from the "Inception Key" (the key used to create it), the binding is mathematical, not administrative. You verify the ID by checking the signature, not by calling a helpdesk.

## 3. Pre-Rotation (The Insurance Policy)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#3-pre-rotation-the-insurance-policy)

This is the Game Changer. In most systems (like Bitcoin), if someone steals your private key, they own your assets forever. KERI solves this with Pre-Rotation.

- The Mechanism: When you create your ID, you cryptographically commit to your next key (Pre-Rotation), but you keep that key hidden offline.
- The Benefit: If your active key is stolen, the thief cannot lock you out, because they don't have the hidden "Rotation Key." You use the hidden key to revoke the stolen one and regain control.

## The Power of AIDs in Practice

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#the-power-of-aids-in-practice)

This architecture translates into massive real-world advantages:

## 1. True Portability

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#1-true-portability)

AIDs are not "Ethereum DIDs" or "Hyperledger DIDs." They are universal. KERI acts as a "Trust Spanning Layer," allowing your identity to move freely between different networks and platforms.

## 2. Flexible Hierarchy (Chain of Command)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#2-flexible-hierarchy-chain-of-command)

AIDs are designed for organizations, not just individuals. They support Delegation.

- A Root Organization, e.g., the Global Legal Entity Identifier Foundation, GLEIF, can delegate to an Issuer.
- The Issuer can delegate to a Company.
- The Company can delegate to a CEO. This creates a verifiable chain of trust that mirrors how real businesses operate (like the vLEI ecosystem).

## 3. Unprecedented Recovery

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%204%3A%20Autonomic%20Identifiers%20\(AIDs\)%20-%20Your%20Digital%20Bedrock.md#3-unprecedented-recovery)

With the combination of Pre-Rotation and a "Watcher Network" (observers who check for fraud), you can detect a hack instantly and recover your identity before damage is done. This level of safety is unique to KERI.


# Veridian - Bringing KERI to the Enterprise

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#veridian---bringing-keri-to-the-enterprise)

## The Enterprise Identity Dilemma

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#the-enterprise-identity-dilemma)

Enterprises today are stuck between a rock and a hard place.

- Option A: Centralized Identity (e.g., Active Directory). Problem: Vendor lock-in and single points of failure.
- Option B: Decentralized Identity (Web3). Problem: A chaotic mess of complexity and poor interoperability.

Veridian exists to solve this dilemma.

It is a platform designed to bring the power of decentralized identity to the enterprise, without the chaos. It wraps the raw power of the KERI protocol suite (KERI, ACDC, CESR) into a usable, scalable product for developers and businesses.

## The Strategic Pivot: Why Not Standard DIDs?

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#the-strategic-pivot-why-not-standard-dids)

When building Veridian, we had to make a choice: Use standard Decentralized Identifiers (DIDs) or use KERI?

We evaluated the DID ecosystem and found a practical challenge for enterprise adoption:

- Interoperability: With over 200 DID methods across different chains, cross-chain identity verification requires complex bridging infrastructure.
- Operational Cost: Enterprises operating across multiple partners would need to support multiple chain backends — a significant infrastructure burden.
- Architectural Trade-offs: “Universal Resolvers” emerged to bridge methods, but they add a layer of intermediary infrastructure that KERI's design can bypass.

We chose KERI because it acts as a universal identity layer that can work alongside any blockchain, including Cardano, rather than competing with one.

You can think of KERI like TCP/IP for Trust. It doesn't care what network you are on. It creates a universal layer where any identity can verify any other identity, regardless of the underlying infrastructure.

## A New Foundation: Autonomic Trust

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#a-new-foundation-autonomic-trust)

Most identity systems rely on Algorithmic Trust (trusting a blockchain).

Veridian relies on Autonomic Trust (trusting the Identifier).

- The Difference: In KERI, the identifier is self-certifying. Its validity is proven by its own cryptographic history (the Key Event Log), not by checking a ledger.
- The Benefit: This makes the identity Portable. You can move your corporate identity from a cloud server to a local data center without breaking it.

## Enterprise-Grade Features

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#enterprise-grade-features)

Veridian selected KERI because its feature set maps directly to enterprise needs:

## 1. Solving Key Compromise (Pre-Rotation)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#1-solving-key-compromise-pre-rotation)

In traditional systems, if a corporate root key is stolen, it is a catastrophe. The company might have to revoke millions of credentials.

With Pre-Rotation, this becomes a manageable incident.

Because the "Rotation Key" is kept offline (cold storage), a hacker who steals the active "Signing Key" cannot take over the identity. The company simply uses the cold key to lock out the hacker and restore control.

## 2. Proactive Security (Watcher Network)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#2-proactive-security-watcher-network)

KERI uses a network of Watchers—think of them as a decentralized security team. They monitor the identifier's history 24/7. If an attacker tries to publish a fake history (duplicity), the Watchers detect it instantly, allowing the company to react before customers are harmed.

## 3. Governance (Multi-Signature)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#3-governance-multi-signature)

Real businesses don't rely on one person with one key.

KERI supports Weighted Multi-Sig.

- For example, you can set a rule that says: "Signing a low-value invoice requires one key (The Manager). Signing a high-value contract requires a weight of three (The CEO + The COO + The CFO)." This allows Veridian to mirror your actual corporate governance structure in code.

## 4. Verifiable Chains (ACDC)

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%205%3A%20Veridian%20-%20Bringing%20KERI%20to%20the%20Enterprise.md#4-verifiable-chains-acdc)

Using ACDCs, we can build chains of trust.

- The Global Legal Entity Identifier Foundation, or GLEIF, Model: The Global Foundation delegates to an Issuer —> Issuer delegates to a Company —> Company delegates to an Employee. This creates a clear, audit-proof path of authority for every action taken by the enterprise.



# ACDC - Beyond Simple Credentials

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%206%3A%20ACDC%20-%20Beyond%20Simple%20Credentials.md#acdc---beyond-simple-credentials)

## The Next Generation of Verifiable Data

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%206%3A%20ACDC%20-%20Beyond%20Simple%20Credentials.md#the-next-generation-of-verifiable-data)

While most are familiar with the concept of a simple, standalone digital credential (like a PDF course certificate), Authentic Chained Data Containers (ACDCs) offer a much more powerful framework. Defined by an emerging IETF specification, ACDCs move beyond isolated attestations to enable complex, verifiable data relationships.

An ACDC is a container designed to prove exactly who authored data and where it came from. These containers are structured as Directed Acyclic Graphs (DAGs). While the term sounds complex, the concept is straightforward: it is a method of linking data where "arrows" only point one way. This prevents circular logic and ensures a clear flow of information.

Each ACDC acts as a "node" that connects to other containers via cryptographically verifiable links, or "edges." This allows us to build digital structures that mirror real-world hierarchies.

## The ACDC Advantage: Key Differentiators from W3C Verifiable Credentials

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%206%3A%20ACDC%20-%20Beyond%20Simple%20Credentials.md#the-acdc-advantage-key-differentiators-from-w3c-verifiable-credentials)

The design of the ACDC protocol unlocks security and flexibility capabilities that other formats struggle to match. The key advantages over standard W3C Verifiable Credentials include:

- **Schema Referencing** (No Link Rot): Standard credentials often use web links (URLs) to define their structure. If that website goes offline or the file moves, the credential breaks. ACDCs avoid this by using a Content-Addressable Secure Hash, aka Self-Addressing Identifiers (SAID), which we expand on later. The rules are locked mathematically, not hosted on a server, ensuring the credential remains valid for decades.
- **Scope of Use**: ACDC is flexible. It supports both targeted credentials (issued to a specific person) and untargeted, signed documents (like a public audit report).
- **Data Chaining**: This is the killer feature. ACDCs are designed to be linked together to form chains. This enables us to model provenance (history) and delegation (permission).

## Unlocking Advanced Use Cases with ACDC Chaining

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%206%3A%20ACDC%20-%20Beyond%20Simple%20Credentials.md#unlocking-advanced-use-cases-with-acdc-chaining)

The true power of an ACDC lies in its "edge" section—cryptographic pointers that allow one credential to reference another. By linking credentials, we create a provable line of authority.

Consider a government authority issuing an Accreditation Credential to a University. The University then issues a Diploma Credential to a Student.

The diploma uses an "edge" to point back to the University's accreditation. When an employer verifies the diploma, the software automatically crawls up the chain. It confirms not only that the diploma is valid, but that the University was accredited at the time of issuance.

This chaining capability unlocks:

Cryptographic Provenance: A tamper-evident chain of custody, vital for supply chains. Delegated Authority: Proving that a manager has the specific authority (delegated from a director) to sign a purchase order. Complex Logic: Chains can include rules. For example, "This Purchase Order is valid ONLY if signed by a manager with a "Budget Authority" credential."

## ACDC in Action: The GLEIF vLEI

[](https://github.com/cardano-foundation/cardano-academy/blob/main/courses/Future_of_Digital_Identity_and_KERI/Unit%206%3A%20ACDC%20-%20Beyond%20Simple%20Credentials.md#acdc-in-action-the-gleif-vlei)

The best real-world example of this architecture is the verifiable Legal Entity Identifier (vLEI) system.

The vLEI uses a chain of ACDC credentials to represent corporate authority:

1. GLEIF (Root): The global root of trust.
2. QVI (Issuer): A "Qualified vLEI Issuer" accredited by GLEIF.
3. Legal Entity: The company itself.
4. OOR (Role): An "Official Organizational Role" credential held by an individual, for example, a CEO.

This structure allows a CEO to digitally sign a document and prove—mathematically—that they have the authority to act on the company's behalf. This model is now an ISO standard (ISO 17442-3).