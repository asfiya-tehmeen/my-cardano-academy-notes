## 1. What is Bitcoin?

### Not the first attempt at digital money

Bitcoin was the first cryptocurrency, but it wasn't the first try at digital money. It built on earlier efforts.

**Timeline**

- **1991**: Stuart Haber and W. Scott Stornetta came up with a way to securely "timestamp" digital documents, chaining them together cryptographically so they can't be tampered with. Clever, but it never took off and the patent expired in 2004.
- **2004**: Hal Finney (a veteran of the original cypherpunk movement) built on earlier ideas with **Reusable Proof of Work (RPoW)**.
    - It tackles double-spending, but relies on a central server for verification.
    - Important stepping stone for later cryptocurrencies.
- **2008**: During the global financial crisis, the pseudonymous **Satoshi Nakamoto** released the white paper _Bitcoin: A Peer-to-Peer Electronic Cash System_.
    - Inspired by an earlier project called **Hashcash**.
    - Introduced a decentralized way to verify transactions with no central authority needed.
    - This is seen as the true birth of blockchain technology.

### Blockchain vs Bitcoin

- People often use the two terms interchangeably, but **Blockchain = the technology**, **Bitcoin = one implementation of it**.
- Bitcoin's big breakthrough was solving the **double spend problem**: a bad actor spending a cryptocurrency twice before the recipient(s) realise only one of the transactions was valid.
- The whitepaper describes it as _"a solution to the double-spending problem using a peer-to-peer distributed timestamp server to generate computational proof of the chronological order of transactions."_

### Cypherpunks and the philosophy behind Bitcoin

- The cypherpunk movement shaped Bitcoin's early development and philosophy. Their values, technical skill and active participation laid the foundation for cryptocurrencies.
- **The problem with fiat money:**
    - Issued and controlled by governments and central banks, with a seemingly endless supply.
    - Most transactions are scrutinised, and bank accounts are sometimes censored or even frozen.
    - Most central banks are moving to fully digital systems, so freedom and privacy risk being sacrificed.
    - Physical cash still allows private, anonymous payments, but it's accepted less and less (lots of businesses are now "card only").
- **Bitcoin is the opposite of this:**
    - Decentralized, peer to peer, censorship resistant, not backed by any government or institution.
    - Every transaction sits on a public ledger that anyone with an internet connection can access.
    - Deflationary asset with a fixed, limited supply of **21 million**, expected to all be mined by **2140**. This softens inflation to some degree and removes uncertainty about current and future supply.
    - New bitcoin creation is set by the protocol and a predefined set of rules.
    - **Mining** verifies and validates blockchain transactions, and creates new bitcoin as a reward.
    - Released as **open source** code, so anyone can contribute to development. Traditional financial systems are usually proprietary code, privately controlled by authorities and central banks.

### The Genesis Block

- **3 January 2009**: Satoshi mined the first block. Reward was **50 BTC**.
- Satoshi embedded a message in it: _"The Times 03/Jan/2009 Chancellor on brink of second bailout for banks."_
- Why it was included was never officially explained, but many read it as an unofficial mission statement for Bitcoin.
- The text is a headline from the 3 Jan 2009 edition of _The [London] Times_, about the government's failure to stimulate the economy after the 2008 crisis.
- Many believe it was a subtle hint that Bitcoin should be the antidote to the contagion spread by the big investment banks that needed government bailouts and sent economies into a tailspin.

### First transaction and the halving

- First recipient of Bitcoin: **Hal Finney**, who got **10 bitcoins** from Satoshi on **12 January 2009** (first bitcoin transaction).
- Roughly every **10 minutes** the supply grows as miners get rewarded for validating transactions.
- **Halving** happens roughly every **4 years**: the reward is cut in half, so inflation drops.

|Year|Block reward|
|---|---|
|2009|50 BTC|
|2012|25 BTC|
|2016|12.5 BTC|
|2020|6.25 BTC|
|19 April 2024|3.125 BTC|

### Is it actually useful?

- A growing pool of investors treat Bitcoin as **"digital gold"**: a viable alternative investment to diversify a portfolio, especially when markets are volatile.
- Fees and transaction times are negligible compared with the traditional financial system, where a money transfer can take several business days.
- Especially appealing for **international remittance**, where some services charge extortionate rates.
- **Notable transactions:**
    - **22 May 2010**: two pizzas bought for **10,000 BTC** (about $40 at the time). 22 May is now celebrated as **Bitcoin Pizza Day**.
    - **10 April 2020**: a wallet belonging to the Bitfinex exchange moved **161,500 BTC** (about $1.1 billion at the time) for a fee of roughly **$0.68**.

### Limitations and criticisms

- **Transaction times** can range from 10 minutes up to a day when the network is busy.
- **Centralization concerns:**
    - Critics say it's less decentralized than Satoshi intended, since the network is mostly professional mining pools (only they can afford the hardware and electricity).
    - Some senior developers have left the project over centralization and lack of governance.
    - Some feel a small core group in the community has too much say over the direction of the currency.
- **Programmability vs expressiveness:** Bitcoin has programmability but limited expressiveness.
- **Resistant to change** by design, mainly for security. Can be seen as a reluctance or inability to innovate. For some that's its biggest strength, for others its biggest weakness.
- **High energy consumption:**
    - The more computation required, the more miners have to spend on hardware to compete realistically for rewards.
    - Barrier to entry goes up and participation becomes more exclusive.
- **Ever-increasing storage requirements:**
    - As the blockchain grows, sync times and transaction settlement times go up.
    - Fewer machines can take part, which may make the network less resilient to attacks and exploits.

---

## 2. How does Bitcoin work?

- Bitcoin achieves **Byzantine Fault Tolerance** by letting all network participants validate blocks and transactions.
- Consensus mechanism = **proof of work**.

### The mining process

1. In a big distributed network of nodes, new transactions get sent to all miners.
2. Miners collect the transactions and bundle them into potential blocks.
3. Each miner competes to solve a complex puzzle for their block, producing a unique identifier called a **block hash**. This shows they put in effort, hence "proof of work".
4. First miner to solve it shares the block with everyone.
5. If everyone agrees the block is valid, it becomes part of the permanent record, the blockchain.
6. Repeat. Each new block references the previous one, forming a secure, cryptographically linked chain.

### Transactions

- A **transaction** is a transfer of value between users.
- The sender references the previous transaction they received, proving they're allowed to spend the value.
- A transaction can have **several inputs** to make up the amount being sent.
- If total output is higher than what the sender wants to transfer, the protocol sends the difference back to the sender.
- Analogy: **"cash in, cash out"**. Book costs 8 coins, you send 10, you get 2 back as change.
- Inputs and outputs must always match: **sum of inputs = sum of outputs + transaction fee** (as written in the module: "sum of inputs = sum of outputs - transaction fee")

### Proof of work (PoW) in detail

- Mining nodes compete to guess a pseudo-random number called a **nonce** ("number used once").
- The nonce is combined with the block data and passed through a hash function until the output meets certain criteria, e.g. a hash starting with nine zeros.
- The target output can be adjusted with the **difficulty level**. If more miners with better equipment are competing, the target might become a hash with twelve leading zeros.
- Goal: **one block mined every ten minutes**.
- Whoever guesses the nonce first gets a set amount of bitcoin.
- The puzzles are **"difficult to solve, but easy to verify"**.
- After solving, the miner shares the block, and all other miners verify the solution is legitimate. This is **"inclusive accountability"**: everyone can "check each other's homework".
- The miner then adds the block to their copy of the blockchain, and the transaction is considered complete.
- The miner also includes the output hash of the previous block, so blocks are chained together.
- Every miner has a copy of the blockchain. Everyone trusts the chain with the **most computational work** in it. That's where "**longest blockchain**" comes from.

### Why it's trusted

- Each valid block has a block hash representing the miner's work.
- Trust comes from the fact that even a small change to the input hash changes (invalidates) the output hash.
- PoW has resisted all kinds of attacks since 2009.
- **51% attack:** a successful attack generally means a malicious attacker getting 51% of the network's mining power. That would take so much time and computing power it isn't viable, because the cost would be greater than any possible reward.

### Mining pools

- A miner's chance of solving the puzzle = their mining power relative to competitors.
- In a **mining pool**, smaller miners combine resources to improve their chances of mining the next block.
- Rewards are split in proportion to how much processing power each member contributed.

---

## 3. Scalability case study: The Lightning Network

- A **Layer 2** payment protocol that runs on top of a **Layer 1** blockchain (here, Bitcoin).
- White paper published **February 2015** by **Joseph Poon and Thaddeus Dryja**.
- Problem: Bitcoin can only process **7 transactions per second**. The paper's solution is to run transactions **off-chain** (away from the main chain).
- Uses user-generated **bi-directional payment channels**, giving almost instant transactions with smaller fees.

### How it works

- A payment channel is opened with an **on-chain transaction**. After that it handles unlimited off-chain transactions without needing on-chain consensus, so they're faster and cheaper.
- To open a channel, two parties set up a **multi-signature wallet** and put some funds in. Think of a safe: funds go back and forth but can only be accessed when both parties confirm with their private keys.
- Each party signs and updates their records after every transaction.
- When they're done, the channel is closed and the latest balance is shared with the whole Bitcoin network.
- **Disputes:** either party can fall back on their updated records and recover their funds.

### How one channel scales to a network

- A single channel is just a simplification. Channels are the building blocks of a large network.
- Even without a direct channel, a payment can be routed through other connected channels.
- Example: Alice wants to pay Bob but has no direct channel, so she uses Fred's channel (a mutual friend).
- The smart contract automatically finds the **shortest route**, even through several channels (hence "Lightning" Network).

### Drawbacks

- The receiving party must be **online** for the transaction to go through.
- Opening and closing a channel still needs an **on-chain transaction**.
- _Later in the course: Cardano addresses some of these issues with a similar solution._

---

## 4. What is Ethereum?

### Origins

- **Vitalik Buterin** (developer, co-founder of _Bitcoin Magazine_) wrote the Ethereum whitepaper in **2013**.
- He argued for a **scripting language for Bitcoin** so developers could build decentralized applications (**dApps**).
- The community couldn't agree (an early test of governance), so Buterin started a new blockchain, Ethereum, to bring programmability in.
- The whitepaper describes an open-source, public, permissionless, blockchain-based distributed computing platform that can run **smart contracts**.

### Smart contracts

- Idea came from lawyer and computer scientist **Nick Szabo** in the **1990s**.
- A smart contract is a **self-executing program** that runs on a blockchain once predetermined conditions are met.
- Ethereum launched in **2015**, and smart contracts were widely adopted soon after.
- Most common use: execute a transaction only if certain conditions are met.
- Written in a high-level language and **compiled into bytecode** (like translating code into simpler code the computer understands better).
- The **Ethereum Virtual Machine (EVM)**, a decentralized, Turing-complete virtual machine, reads and runs the contracts using a global network of public nodes.
- This is where **"world computer"** comes from: an immutable, transparent blockchain on a resilient network gives censorship resistance.

### Solidity

- Language used for Ethereum smart contracts. Built specifically for Ethereum, similar to JavaScript, so easy to pick up for new blockchain developers.
- **Downside:** some experts think it's too expressive, so it's easy for "unintended side effects" to creep into a dApp's code.
- Common bug example: **incorrect access control** (contracts lack enough access controls on code that executes critical logic).
- Smart contracts enable a wide range of use cases (covered later). Developers could now build and publish dApps on Ethereum.

### Ether and gas

- **Ether (ETH)** = Ethereum's cryptocurrency.
- Transaction fees are paid in ether and are called **gas**. More computation = more gas.
- The same transaction can cost different amounts of gas at different times, depending on network demand.
- Your transaction's priority depends on how much gas you're willing to pay.
- _Later: how Cardano tries to address these issues._

### NFTs

- Ethereum led the rise of **NFTs** (non-fungible tokens): cryptographic tokens that represent a **unique asset**. Think of them as tokenized certificates of authenticity and ownership on a blockchain.
- **Non-fungible** = not interchangeable. This creates **"digital scarcity"** and opens up lots of use cases (covered later).
- **Fungible** tokens still matter. Fiat currencies and most cryptocurrencies (Bitcoin, ether, ada on Cardano) are fungible: interchangeable and practically indistinguishable in everyday use as a medium of exchange.

### ERC standards

- To create an NFT on Ethereum you have to follow **ERC (Ethereum Request for Comment)** standards, a collection of guidelines for doing different things on the chain.
- **ERC-20**: lets users create ("mint") indistinguishable (fungible) tokens.
- **ERC-721**: covers issuing and trading **non-fungible** assets.
- **ERC-1155**: enhancement that lets a **single contract hold both fungible and non-fungible tokens**, widening the possible use cases.
- _Later: Cardano innovated in NFTs with **Native Assets**._

---

## 5. Proof of Stake (PoS)

### Background

- Alternative consensus mechanisms appeared to address the shortcomings of PoW.
- PoS was first floated on the **Bitcointalk forum in 2011**.
- Both reach consensus, but in quite different ways. There are also different PoS implementations (more later).

### How it works

- Uses a **random election** to pick a node as validator of the next block.
- Selection criteria vary by blockchain, but generally include **staking duration, amount of stake, randomization and node strength**.
- **Validator** = entity responsible for validating the next block.
    - Bitcoin: the miner or mining pool.
    - Ethereum: the stake pool.
- In PoS, blocks are **forged**, not mined.
- Reward is usually **transaction fees**, though extra incentives can be offered.
- Participants in forging must **commit** a set amount of coins = their **stake**.
- Bigger stake = better chance of being picked. Lottery comparison: more tickets, better chance of the winning one.

### Selection methods

- **Randomized Block Selection**: validators chosen based on a combination of **lowest hash value and highest stake**.
- **Coin Age Selection**: nodes chosen by how long their tokens have been held. Calculated as **days held × number of coins**.
- After forging a block, the node's **coin age resets to zero** and it has to wait a set period before it can forge again. This stops someone with a big stake having too much control.
- Every blockchain does PoS differently, with its own rules and configuration.
    - e.g. **Algorand and Cardano** use the **Verifiable Random Function (VRF)**, one of cryptography's most important discoveries, dating back to **1999**.

### Staking ETH

- Staking ETH means supporting a validator for the network.
- Randomly selected validators who hold a minimum amount of ETH verify transactions and add new blocks.
- Validators and their stakers earn rewards through **freshly minted ETH and network transaction fees**.

### Security: skin in the game

- The stake motivates the forging node to behave honestly because it has "something at stake".
- Fraudulent nodes can lose **part or all** of their stake, plus the right to forge in future.
- **51% attack** in PoS works like in PoW, except the attacker needs a **majority stake (51%)**. Highly unlikely unless the cryptocurrency's value is very low.

### Pros of PoS

- Energy efficient.
- Secure.
- More inclusive: running a node is usually easy and affordable.
- High participation plus randomization makes the network more decentralized, since **mining pools aren't needed** to mine blocks.
- Caveat: not all PoS blockchains are equal.

### Things to consider before staking on Ethereum

- **September 2022**: the Ethereum **"Merge"** moved the chain from PoW to PoS. This is only one step on a long Ethereum 2.0 roadmap.
- Need a deposit of **32 ETH** to run a staking node.
- There's a **lockup (bonding) period** where funds can't be accessed.
- **Slashing**: penalty to deter dishonest validator behaviour. Can mean losing a validator's staked ETH and even removal from the network.

### Delegated Proof of Stake (DPoS)

- Extends the PoS idea. Originally developed by **Daniel Larimer in 2014**.
- Coin holders **delegate** to a validator (like voting for a politician), handing over the staking responsibility.
- More efficient, since many users lack the technical ability or time to run a validator.
- Democratic: low barrier to entry, can be a one-time delegation.
- Otherwise works much like PoS.
- _Later: Cardano is the first provably secure PoS protocol, years before Ethereum transitioned._

---

## 6. Hard Forks & Soft Forks

- **Question:** with no central authority and nobody in charge, how does a blockchain get updated? Answer: **soft forks or hard forks** (a bit more nuanced than that, since some chains implement them very differently).
- All software needs regular updates to fix issues, boost performance and defend against new attacks. Comparison: Microsoft's **Patch Tuesday** (Update Tuesday, second Tuesday of every month). Blockchain equivalent = **forks**.
- A decentralized network works best when all nodes follow the same rules and run the same node version. These rules are the **protocol**. A fork can change the protocol's behaviour by different amounts.

### Soft fork

- **Backwards-compatible** upgrade.
- "Soft" because it doesn't necessarily interrupt normal network operation.
- Like an optional update on your laptop.

### Hard fork

- A more drastic protocol change.
- Nodes that don't update generally **can't process transactions or add blocks to the same blockchain**.
- Used for major protocol updates, or literally to split a blockchain in two: the old chain carries on as before and a new chain is created with different (sometimes contentious) features.

### Example 1: Ethereum / Ethereum Classic (the DAO hack)

- A **DAO (Decentralized Autonomous Organisation)** was hacked because of a Solidity vulnerability, and about **3.6 million ETH** was stolen.
- Split the community: no consensus and no governance mechanism to decide what to do.
- Ethereum chose to **reverse the hack and refund the ETH**.
- **Ethereum Classic** took a **"code is law"** stance: those who lost ETH should "take their medicine".
- This led to a contentious hard fork and two separate chains: **Ethereum** and **Ethereum Classic**.

### Example 2: Bitcoin Cash

- The scaling conundrum led to heated debate and the creation of **Bitcoin Cash**, a fork of the original protocol with the maximum block size raised to **32MB**.
- Bitcoin has been forked **over a hundred times**.

### Note

- Hard forks aren't only technical events. Intangibles can motivate communities. Ideally they're planned and unanimous, but they can also be sudden, controversial and traumatic.

---

## 7. The 3 Generations of Blockchain

Since Satoshi's white paper, blockchain has evolved through three generations, each with new features and capabilities.

|Generation|Led by|Key points|
|---|---|---|
|**1st**|Bitcoin|Proof of work. Energy intensive but very secure. Reluctant to add features for fear of a bigger attack surface and a less secure network.|
|**2nd**|Ethereum|Programmability via smart contracts in Solidity. Blockchain became more than moving currency around, and dApps brought lots of new use cases. Started as PoW, moved to PoS in Sept 2022.|
|**3rd**|Cardano, Polkadot, Algorand|Extends past projects. More emphasis on **scalability, interoperability and governance**.|

**1st gen detail:** miners need ever-increasing computing power by design to compete for new blocks.

**3rd gen detail:** Cardano was the first PoS blockchain to offer the **same security guarantees as Bitcoin**. It takes a **research-driven approach** with many novel features and solutions (explored in the next videos).

---

## Quick reference: key terms

- **Double spend problem**: spending the same crypto twice before the recipient knows only one transaction was valid.
- **Nonce**: "number used once"; the number miners guess in PoW.
- **Difficulty level**: adjusts the target hash to keep block time at ~10 min.
- **Halving**: block reward cut in half roughly every 4 years.
- **Layer 1 / Layer 2**: base blockchain / protocol built on top of it (e.g. Lightning).
- **Smart contract**: self-executing program that runs when conditions are met.
- **EVM**: Ethereum Virtual Machine, runs smart contracts.
- **Gas**: fee paid in ETH on Ethereum.
- **Fungible / non-fungible**: interchangeable / unique.
- **ERC-20 / 721 / 1155**: fungible tokens / NFTs / both in one contract.
- **Validator**: entity validating the next block (miner in PoW, staker/stake pool in PoS).
- **Forging**: block creation in PoS (vs mining in PoW).
- **Slashing**: penalty for dishonest validators in Ethereum PoS.
- **VRF**: Verifiable Random Function, used by Algorand and Cardano (dates to 1999).
- **Soft fork / hard fork**: backwards-compatible upgrade / drastic change that can split the chain.