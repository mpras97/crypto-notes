https://medium.com/coinmonks/cosmos-tendermint-explained-for-real-idiots-ab4305cbb41

Tendermint - software | Cosmos - blockchain or main hub for internet of blockchains
Cosmos - **Byzantine replicated fault machines** in any programming language
BFT -> no single trusted entity for release of coins.
Byzantis Generals Problem: 
Eg. Older times | Centralised info sharing not possible | Better methods of decentralised info sharing | How to ensure traitors and loyal generals have correct information.

The generals problem is interesting because it is similar to a decentralized system, which can not be coordinated via a centralised authority directly.

The next scenario is **replicated state**, which is what network of blockchains does. They replicate states across all nodes. For eg. in the case of bitcoin, the unspent transactions are replicated. Wrt bitcoin, they have POW for the solution to BFT.
Tendermint - distribute the state of something across the globe without a central authority.
The replicated state can be: db of pictures, unresolved trade orders etc. Thus, with tendermint, one can one can create the required blockchain system, and only the application logic, and everything else is done. Thus, how nodes connect, how they reach consensus and how the blockchain is written is already solved. We need to program only the economy of our token.
There are though, certain limits. Such as the application should be deterministic. Whatever input we give, we should get the exact output. Thus, tendermint seperates consensus and network layer from each other.
Thus, anybody can write programs on blockchains without writing crypto and networking related code.

How POW solves the mining problem? The approach secures bitcoin. The job of the bitcoin miners is to solve a hard task. The one who solves the task first, finds the block, and proceeds to move on to the next task. Though, how do we know if the guy worked on the correct solution? This is where longest chain rule comes in. ie, the one who has solved the most problems and has the longest chain is the one to go ahead with. How do we trust the guy? Well, the idea is this guy has spent a lot of money in hardware(done a lot of work), and electricity, and thus should be honest because if dishonest, he though, would be able to own lots of bitcoins, would drive down the prices of bitcoins too much, making his investments useless. Also, the difficulty of the work is adjustible. Thus, the one who solves the first problem will get difficult problem later and so on.
The problem with POW is that 1. it wastes a tremendous amount of energy and secondly, most miners don't use cryptocurrency but are responsible for driving up the prices of bitcoin exponentially making it unusable. Thus, if we do a transaction of 10$, and the transaction cost is more than this, it is useless to transact in bitcoin.

Understanding POS:
The network is not secured by hard work but rather by high stakes. In POW, everyone has a chance of minting new blocks based upon their hardware equipment, in POS, everyone has a chance of validating new blocks based upon their stakes in the game. Similar to how expensive hardware made the bitcoin network secure, here the high stakes makes the blockchain network secure. In case, we forged the transactions, the staked currency becomes useless. Thus, the coins become immovable in case of entering validator scenario. Although, this seems pretty logical on top view, there are some problems. A prominent example is **nothing at stake** problem. The idea is simple, since there is no proof of work, the validators are incentivised to validate the forks alongwith the original chains. So, they earn double incentives, making it easier for a bad actor to forge transactions and make it the original chain. This plays with the authenticity of the network, and creates a problem.

### Talking about cosmos:

Cosmos solves nothing at stake problem by introducing **concept of slashing**. Misbehaving validators have their coins slashed, and forging incorrect transactions have a lot of their coins slashed. Also, if you don't participate in staking, you get your coins slashed. This creates dynamic inflation, and since the validators have staked their coins, they get a share in the dynamic inflation.
The next problem that cosmos solves is by delegated Cosmos PoS. If there are 10kstakers in the network, everyone has to inspect the new block and communicate to everyone if it is ok? Thus, two limitations: **latency and bandwidth**. Also, solving this problem results in BFT.
The solution to this problem is delegation. The stakers are split in two groups: the delegators and validators. Validators are part of consensus mechanism, and delegators are not part of direct network communication. We limit the number of validators to a fixed number of nodes. Thus, synchronizing this is not that difficult. How do the delegators participate in the network? Well, the task of delegatorss is to vote on the validators, thus, earning a stake in the validated rewards. The point to note here is that if the validator gets slashed, the related delegators also get their coins slashed.

Thus, this solves the problem via PoS, but the question is how does it differ from other PoS networks?
The thing is cosmos is a multi-token platform. One can not only have atoms which are the staking tokens for cosmos, but also photons which are the fee tokens in cosmos. Since, photons are not staked, they are very fluid at exchanges. Thus, ETH holders get photons and can use ethermint just as ethereum, with much less fees and connected to the Cosmos network.
Cosmos hub has multiple zones connected to it(one is ethermint for ethereum). Thus, one can trade between any different zones without any issues. This helps in properly networking the entire traffic as required. This helps in horizontal scaling. For cosmos, the hubs and zones are built by the users seperately.
