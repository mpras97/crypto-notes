https://juliankoh.medium.com/5-differences-between-cosmos-polkadot-67f09535594b

## Application specific blockchain vs smart contract blockchain:

Own application specific blockchain allows to have more customisability wrt the blockchain application unline smart contract, where one is limited by the smart contract language.
Second reason is sovereignity. Building an application on a smart contract platform means that the application is bound by rules of the smart contract platform. Sovereign chain gives the ability to seamlessly communicate with other applications because they live on seperate blockchains with seperate state machines. Cosmos has hub-and-zone model for this task, and Polkadot has relay chain/parachain model for the same.

### Difference #1: Local vs Global Security:

#### Polkadot
Parachains are blockchains within the polkadot network, such that the chains have their own state machine, their own rules and own block producers. Each parachain is an independent state machine, and can utilize any type of unique functionality, consensus algo, transaction cost structure etc. In polkadot, the parachains are children of relay chains, which is a representation of "global state" of all the parachains combined. Relay chain has its consensus algorithm called GRANDPA consensus, which finalizes blocks on the parachains quickly. 
Thus, this is good for parachains, as once they connect to the relay chain, there are 1000s of validators, and any parachain benefits from the entirety of the validators in the relay chain.
The drawback to this is that the validators in the relay chain have the final say for the validation of the para chain blocks. Thus, selected validators can completely stop the blocks from a specific parachain. This is controlled by randomly shuffling the to-validate blocks, but still a possibility. Polkadot also has another class of validators called fisherman, who continuously checks the validators for malicious activity.

#### Cosmos
Here, every blockchain is independent unlike the local/global security in polkadot. Each blockchain runs its own consensus, and validators of each blockchain are responsible for that blockchain alone. Cosmos uses *hub and zone* model for interoperability, where zones(independent blockchains) can send data to other zones(independent blockchains) via hubs(independent blockchains), using the IBC protocol. Comparing this model to polkadot, the biggest difference is that the state of each zone is secured by its validators alone. Thus, if a zone wants high security, they can recruit their own validators, which may be difficult for smaller applications.
For eg. binance is bootstrapping their dex by having their own nodes as validators for the binance chain as a starting point.

### Difference #2: Governance and Membership
#### Polkadot
Single relay chain and some number of parachains that the validators of the relay chain can support. Currently there are 100 slots for parachains but the number can shrink or grow in the future. Polkadot network allocates slots for a fixed duration based upon staking the DOTs owned by the users. Thus, to become a parachain, one needs to purchase a large amount of DOTs and lock them up for long to continue being a parachain.
Wrt governance, the decisions are taken by amount of DOTs, voters have. There is regular stake voting, and council based voting. Council can change rules of voting etc, or block reward etc, but can not remove a para chain from a relay chain

#### Cosmos
Cosmos network doesn't have fixed rules of membership and thus, anyone can build a hub or zone. Hubs are sovereign chains meant to connect to another chains. Due to this, the inter chain communication is much faster and efficient since instead of connecting to any other blockchain, each blockchain connects to a single hub only.
In case of cosmos, there is no single governancce process, and each hub and zone have their own governance process. Thus, when people talk about governance they are referring to governance of cosmos hub, which is a blockchain launched by the tendermint team.

### Difference #3: Inter-blockchain communication
Polkadot is about passing arbitrary messages between parachains. Thus, one parachain can call smart contract in another parachain and vice versa(ICMP).
Cosmos though, focuses on asset transfers between the chains(IBP)
[MORE DETAILS : IGNORING RIGHT NOW]

### Difference #4: Consensus Algorithms
Polkadot uses the algorithm called GRANDPA. Polkadot provides SDK with 3 out of the box algorithms: GRANDPA, Rhododendron and Aurand.
Cosmos currently focuses only on its own Tendermint Consensus algorithm.

