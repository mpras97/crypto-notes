https://medium.com/coinmonks/polkadot-vs-cosmos-vs-ethereum-2-0-for-real-idiots-3b6f0e0cfb2f

# Blockchain 3.0:
Mainly focuses on:
1. Scalability
2. Isolatability
3. Developability
4. Governance
5. Applicability

## Section 1: Explaining these major factors
### Understanding the basics:
#### Scalability

Scalability refers to the factor of how much extra scalable can the app be made with adding extra network capacity?
The scalability factor for a normal bitcoin protocol is zero. The transaction fees is extremely high.
In fact, wrt ethereum, it becomes even more difficult because of the gas required for the extra smart contract computations done on the ethereum network.

#### Isolatability

Or compatibility. This refers to how compatible the given blockchain is with customised applications written on top of the blockchains. The point is that a platform should be compatible for most things. Thus, for eg if we want to create minecraft, it is difficult to create it on ethereum as the computation price would be extremely high.

#### Developability

This refers to both the User Experience (UX) and Developer Experience (DX). For eg. a huge advantage of ethereum is that you don't need any infrastructure to host your projects. Simply create your project, and deploy it. It will start working on the ethereum blockchain. At times, smart contracts are not recommended, and might not even be safe. There can be hacks such as the DAO hack because of which eth split into two systems, Ethereum and Ethereum Classic. 
So, the entire ecosystem depends upon a few factors. These are mainly:
1. How good is the ecosystem? Usage?
2. How good is the infrastructure? Usage?
3. How strong is the foundation of the platform?

#### Governance

The question is how governable is the blockchain platform? Many older projects lack it, while the newer projects prefer it. For eg. wrt bitcoin, there are 3 parties: miners, users and developers. Miners would want higher transaction costs to make money, while users would want lower transaction costs to use it regularly for transactions. If developers work on new features, they would want to implement it and need the others to come onboard. Ethereum is governed by Ethereum Foundation. The backing of a proper foundation behind a cryptocurrency means that there is a set direction for the project

#### Applicability

Being a great platform is a killer feature. Other projects automatically develop on top.

### Understanding the basics:
#### Scalability:

Vertical vs Horizontal Scaling. One problem with horizontal scaling wrt bitcoin is it is not  possible to scale by creating copies of bitcoin repos. Secondly, there are technical limits wrt vertical scaling. PoW and longest chain rule can be scaled up by increasing block size and reducing block time **theoritically**. Reducing the block time increases centralization in the entire bitcoin network.
Well, the new blockchains try to solve both the problems. They try solving vertical problem using PoS, while the horizontal scaling problem by supporting interactibility between the various blockchains. This is because unlike PoW, PoS doesn't need to solve a probabilistic puzzle. Though, with PoS another problem called N square problem comes in. The point is that once a block is validated, the information of the block validation needs to be shared to all the (n-1) nodes. Thus, each of the validator nodes need to talk to each other leading to a N squared complexity.
One of the most common method to solve the above problem is to use validators/delegators. The delegators delegate the powers of validator nodes, ensuring no cartelization. Since, the number of validators decreases due to this, the above time decreases. Also, more validators are encouraged for partition tolerance. But, in this case the partition tolerance ends up lower than bitcoin.

POS does have other problems though. Two major problems are Long-Range-Attack and Nothing-at-Stake.
What is the Long-Range-Attack? So, in case of PoS, one of the validators can start with a certain percentage. Since, the forging of blocks doesn't cost anything. He can forge new blocks from genesis, creating an entirely new chain. Although, the other validators won't agree on this newly created chain, for a new entrant, this will become a problem to decide which currency is preferred. This problem doesn't come in bitcoin because of the addition of the longest chain rule, and the fact that PoW takes a lot of energy to process the transactions.
But, this is not reciprocable in PoS blockchains. So, how do we do it? Probably using checkpointing. This means that there is no way to reciprocate certain blocks, and there can be no alternate blocks to pass them. This is the rule of **finality**. This is not possible in bitcoin because bitcoin doesn't have any concept of state associated with it. In PoS/BFT, the finality is coded into the blockchain itself. When 2/3 of block is validated, it is considered final.
The Nothing at Stake problem comes in PoS. With bitcoin, this is never the case but only present for PoS coins. Because it is not possible to solve for multiple forks, as one might not get the incentives in that case. 

This entire combination of **BFT + PoS + Slashing** makes the misbehavior for PoS blockchain validator nodes costly. The same thing applies for **PoW + Longest-Chain-Rule**, where misbehavior leads to you wasting a lot of ur resources. Both of them have their tradeoffs, but one doesn't destroy the planet in case you are wrong.
Why PoS is faster is because in nakamoto consensus, the processing of blocks to solve the cryptographic hash function takes a lot of time. To make the game fair, the time taken for solving the cryptographic puzzle should be much higher than time for processing the transaction. Eth has slightly different concept than bitcoin, due to concept of uncles but it doesn't bring such a huge optimisation to the block processing times.

The above is wrt vertical scaling. Now, we see the scenario wrt horizontal scaling. Two cases interoperability and sharding. Interoperability means compatibility, as it connects blockchains together.
**How to have trustless transactions between two blockchains?**
Well, one method is to have a set of people to validate the transfer of cryptos from one type to another decentrally. Thus, these guys come together to validate the transfer of cryptos from one type to another. They might have incentives to cheat the system. Thus, we introduce the concept of slashing. Thus, these guys will have their cryptos slashed in case they decide to try to cheat the system. But another problem can happen with a fork. What if there is a fork such that in it, the sender never sent the money but the receiver received it? This can be handled by the idea of **Peg-zone or Bridge**, which takes bitcoin and creates pegged bitcoin for that, which takes bitcoin and creates pegged bitcoin around that. The minted/pegged bitcoin is burned and the real bitcoin is sent to that address.
[SKIPPING FINALITY POS BECAUSE OF COMPLICATED. WILL READ AGAIN]

**Sharding**: Sharding scales similar to interoperability, with a difference that unlike having multiple blockchains in parallel, in sharding the single blockchain is divided into multiple shards(parts). There is a huge difference between two because in previous case it tries to create a copy of the chains, while in another a single chain is divided via workers. Thus, the major questions for the two is different in the sense that previously, the question was how to make the disjoint parts safely, while in the next case, the scenario is how to organize the organizers such that they don't corrupt the original chain.
Here, the workers of the infrastructure are divided and no worker does all of the work, we get an idea why sharding is good for scaling. The work is producing blocks and the workers are the validators. Sharding allows to split up this work, so that only a small fraction of the validators work on the same part of the network. The reason why Nakamoto Consensus does not scale up with more nodes is that every node _has_ to do all the work. If we split up the work over many nodes, then having more nodes means we can split up the work in more pieces, making every piece smaller and thus enabling scaling. So the idea is that an incoming transaction goes to a shard and is processed there. It gets included in the block on this shard and the other shards do not really need to bother about this transaction.

[READ THIS SECTION ONCE MORE]

#### Compatibility

This refers to 5 different factors:
1. Security
2. Storage
3. Computation
4. Hard Features
5. Token-Economy

1. Security: The point is if the amount to trade in cryptos is much more than the worth of miners, there should be enough security for the crypto owners.
2. Storage: A platform should be able to store whatever data the application needs. Sharding or interoperability makes it easier to handle data
3. Computation: Computation is expensive and there are a lot of improvements on layer-2. Different applications wrt computation needs and overlaps with storage. For eg. games may require much higher computation but less security required unlike defi, where computation can be slower but security needs to be highest.
4. Hard-Features: Functionalities that cannot be plugged in afterwards. Eg. smart contractss can not be written on top of bitcoin. For eg. zero knowledge computing. Anomymity is one reason for this, but there can be other reasons wrt governance etc.
5. Token Economy: How compatible a platform is with the desire to run its own token economy. For eg. a smart token can mint its coins from ethereum but one can not change the fees that is charged or how the flow of fees should be? So, smart contract owners don't make a fee by default. For eg, if we use Uniswap, we pay the transaction fees of ethereum as well as to the owner of the smart contract. Unlike Uniswap, there can be blockchains in the future, which run their own crypto platforms with lesser friction.

#### Developability:

Hard Features are a huge factor for developability. Earlier, to create new projects, devs decided to fork the bitcoin repo and create their own solutions. This can lead to lot of repetition. A better approach would be seperation of layers and modularity. Most prominent would be seperation of network, consensus and application layer.
This is similar to js. Being able to combine different parts of js via nodejs libraries makes the coding process lot more simpler. The Blockchain 3.0 intends to make these improvements. One can either host their blockchain solution seperately or use pooled security measures for hosting their blockchain solutions.
Though, one important point to note here is that the blockchain solutions should be standardized. If the communication between the blockchains is standardized, it doesn't matter what language or protocol etc is used to build the crypto, it works flawlessly.

#### Governance:

While cryptocurrencies are meant to be decentralized, governance is still a very important factor to take care of. For eg in bitcoin, there are 3 major players -- the users, the miners and the developers. Each of them want different goals with bitcoin. This is a major reason why there are so many forks on bitcoin. In Ethereum there is Ethereum foundation and its founder, who has a long term vision for eth, and intends to take it through unlike many other crypto founders.
PoS helps in this regard, as the power relations are more aligned from the beginning. Here, the decision of a future direction of the currency can be based upon voting by the related nodes.

## Section 2: General solutions to these problems and their implications

## Section 3: How the 3 major players are handling this?
## Next discussing the currencies:

### Cosmos:

It has following design goals:
1. Multi-token: Support any number of tokens/coins in the crypto space.
2. Bottom-up: The system is designed from a bottom-up mindset, and there should not be systems at the top directing the bottom parts of the network.
3. Building blocks: Cosmos and its blockchains are built with the idea of building blocks. One example for this is the seperation of network layer, consensus layer and application layer. Different requirements in the project can be easily added without any problems.
4. Stop energy waste: High energy wastage in PoW can be avoided via PoS.
5. Interoperability as protocol: It tries to come up with the idea of interoperability b/w different blockchains. So, one only needs to use the cosmos tool for interoperability, and not their blockchain specifically.
6. Internet of blockchains: Wants to create a place where blockchains can interact with eaach other, and no need for them to work in silos.
7. Overcome "One coin to rule all" mentality: One coin to rule all means that a blockchain tries to accumulate all dApps in its main chain, forcing them to buy their coin.

Tendermint: It is an implementation of BFT. It alone is not permissionless and needs to be made permissionless by introduction of 

