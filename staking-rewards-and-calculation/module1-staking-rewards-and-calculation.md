The Cardano foundation has released an open source rewards calculation with the goal of empowering transparency and community involvement for a stronger network. Before we dive in, let's recap how staking on Cardano works…

In proof-of-stake blockchains, as with proof-of-work, nodes compete with one another to produce blocks. However, they do not compete with hashing power. Instead, they leverage the number of blockchain tokens they control. In both proof of work and proof of stake, the chances of being selected as a block producer is like a lottery. In the former, hashing power determines the proportionality, while in the latter, the number of tokens does. The general idea is that a mechanism elects one actor in the system to produce a block at any one time..

Cardano's proof of stake consensus algorithm pseudo-randomly selects block producers. The distribution of tokens among all block producers forms the basis for the random function. A block producer's chances of being chosen to produce a given block increase proportionally to the number of tokens they hold compared to other block producers..

**Pledged, delegated and active stake**

To increase their chance of being selected, block producers, also called Stake Pool Operators, or SPOs, work towards increasing their token ownership or stake. We refer to the number of tokens a block producer personally owns and contributes to block production as their pledge.. Cardano users who do not directly participate in block production can increase a block producer's chance of being elected by delegating their stake to that block producer through their wallets.

Fig. 2 Pledged and delegated stake

**Live stake vs Active stake** Live stake represents the total amount of stake that a stake pool controls. It combines the stake that is owned by the pool operator with any stake that has been delegated to the pool by other ada holders. Note that if this live stake is recorded in a snapshot, we call it the active stake. However, my live stake and active stake could be different if some of my delegators, for example, change their delegation after the system takes the snapshot. Live stake refers to the current stake at this point in time, while the system uses the active stake in the rewards calculation. SPOs are the entities that leverage the active stake for block production. The higher the SPO’s active stake, the higher the chance of being selected to create and add a new block to the blockchain.

…An essential trait of Cardano's delegation system is that the stake remains liquid during the entire process. Said differently, there's no locking. Delegated funds can be transferred freely, and with them, their associated delegation rights.

**Stake Distribution Snapshots**

This raises an interesting question: if the stake is fully liquid, how can we pin down the exact amount of stake used for the lottery? The answer lies in the protocol and stake distribution snapshots.

Ouroboros divides time into 1 second slots, with blocks filled, on average, every 20 seconds. Slots are grouped into epochs lasting 5 days on mainnet currently. Many protocol mechanisms actually rely on these epochs and you’ll often hear mentions of “epoch boundaries” in the context of Cardano. This refers to the moment where the system transitions from one epoch to the next.

From a consensus perspective, we almost always look at a snapshot of the stake distribution across an epoch and a fair question is, “a snapshot of what?” The system takes a snapshot of the stake distribution at the beginning of every epoch, reflecting the distribution from the previous epoch. However, it doesn't use this snapshot immediately because the system doesn't consider it stable yet. This delay occurs due to the probabilistic settlement of transactions in the system, which means that the system only settles information after a certain period.

Let’s illustrate this with an example. If I delegate my stake in epoch n, the system will include it in the snapshot that occurs at the boundary between epoch n and n + 1, but it will only use it for the slot leader schedule of epoch n + 2. The system always allows at least one entire epoch for the stake to truly become active.

**Consensus rewards and reserve**

The first kind of incentives we find in the system are consensus rewards… Ouroboros awards stake pools for their work through consensus rewards proportional to the blocks they produce. These rewards have two different sources: transaction fees and the reserve. Transaction fees are self-explanatory and correspond to the fees the system collects on all transactions in each block, per epoch. The reserve is a pot of unallocated Ada tokens the system set aside at Cardano’s genesis and hasn’t issued yet.

Note some outliers exist, which the report details more, that are not part of the circulating supply. In every epoch, the system puts a certain percentage of the reserve into circulation through rewards.

That percentage we call the monetary expansion and typically denote it as ρ (Rho). It is a configurable protocol parameter whose value the system currently sets at 0.3%. Thus every epoch, a maximum of 0.3% of the unallocated Ada is put in circulation, and since the reserve does not replete, this amount gradually gets smaller. At this rate, the system halves the reserve roughly every five years.

Note that the exact amount put in circulation depends also on the blocks produced during that epoch. If the system only produces half the blocks it was expected to produce, it puts only half of the planned monetary expansion into circulation thus making the creation of new tokens entirely proportional to the actual block production. Due to the current ledger rules it could happen, that the reserve grows, if ρ (Rho) becomes very small, then that the fee pot would make the majority of the total rewards pot.

**Stake rewards and pool parameters**

On the other hand, delegators are also incentivized. In exchange for their delegation, ada holders receive a proportion of the rewards the stake pool earns according to parameters both fixed by the protocol and set by the stake pool itself.

A flat cost is taken from the total rewards granted to the pool with a minimum imposed by the protocol. This minimum is known as “min pool cost,” and it currently sits at 170 Ada. It is meant to cover the cost of running a stake pool. Then, the pool sets a variable cost–or pool margin–as a percentage. On Cardano, most pools oscillate between 1% and 3%. Once the system deducts this cost from the pool rewards, it splits the remainder across all delegates proportionally to the stake they contributed to the pool.

Another particularly interesting parameter is called the pledge. The pledge represents a minimum amount of stake that pool owners commit to delegating to their own pool as a testimony of their seriousness and involvement. Note that pledge is optional, but think of it as a gesture by the SPO to have “skin in the game.” A high pledge means that the pool is more likely to produce blocks–and thus generate rewards–even if it hasn’t yet attracted many delegators. Pools declare the pledge when registering, and they must meet it through delegation. Should a pool not meet its declared pledge, it would receive no rewards from the system at all.

Attracting delegation is not an exact science. Besides marketing and branding, some parameters provide a means for stake pools to compete with one another. A higher pledge or a lower variable fee is usually good to attract delegators. With incentives for stake pools, delegators, and liquid staking, Cardano ensures that a high amount of the total available stake takes part in the consensus at all times, helping secure the network against malicious actors.