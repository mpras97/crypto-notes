# Cosmos white paper:

### Introduction:

Public cryptocurrencies inspired the info that decentralized protocols can be used to radically improve socio-economic infrastructure. But, there are few drawbacks to current blockchains:
1. Gross energy inefficiency
2. Poor or limited infrastructure
3. Immature governance mechanisms

Scaling bitcoin throughput through Seggregated Witness and BitcoinNG doesn't work since they are limited to a single CPU to ensure property of bitcoin auditability.
An ideal solution to apply parallel blockchains to interoperate while maintaining their security properties has proven really difficult because of increased work on the parent chain to handle child chains and secondly due to the parent merge mining creating problems for child merge mining.

*Cosmos* to address these issues. It is a network of many independent blockchains called zones. The zones are powered by Tendermint BFT, which provide high-performance, consistent, secure PBFT like consensus engine, where strict fork accountability guarantees control over malicious actors.

First zone of cosmos is called Cosmos Hub. Cosmos is a multi-asset proof of stake cryptocurrency with simple governance system, which enables the network to adapt and upgrade. Also, the cosmos hub is extended by connecting other zones.

The hubs and zones of the Cosmos network communicate by IBC(inter-blockchain communication) protocol. Tokens are transferred from one zone to another without exchanging liquidity between zones. The hub isolates each zone from the failure of other zones.

## Tendermint:

We describe the Tendermint consensus protocol and the interface used to build applications with it.

### Validators:

In classical BFT algorithms, each node contains the same weight. In Tendermint, nodes that have positive voting power are called Validators. Validators participate in the consensus protocol by broadcasting cryptographic signatures, or votes to agree upon the next block.
Validators' voting powers are determined at genesis, or changed deterministically by the blockchain, depending upon the application. For eg. in cosmos POS app, the voting power may be determined by the amount of staking token bonded as a collateral.

### Consensus:

Tendermint is known for its simplicity, performance and fork-accountability. Protocol requires a fixed known set of validators, where each validator is identified by their public key. Validators attempt to come to consensus one block at a time, where a block is a list of transactions. Voting for consensus on a block proceeds in rounds, where each round has a round leader who proposes a block. The validators then vote on whether to accept the new block or move to the next round. The proposer is chosen based upon their voting power.
Tendermint consensus can process thousands of transactions per second, with commit latencies in order of one to two seconds.

### Light Client:

Light client security making it ideal for mobile and IoT use cases. While bitcoin light client must sync chains of block headers to keep the one with the best POW, tendermint light clients need to keep up only with the changes to the validator set, and verify 2/3rd pre-commits in the latest block to determine the latest state.

## Preventing Attacks:

Tendermint has protective measures for preventing certain notable attacks, discussed later on.

### ABCI:

Tendermint consensus algorithm is implemented in a program called Tendermint core. Tendermint BFT is an application agnostic consensus engine that can turn any deterministic blackbox application into a distributed replicated blockchain. Tendermint BFT connects to blockchain applications via Application Blockchain Interface, which defines the boundary between replication engine and state machine. Thus, ABCI allows blockchain applications to be written in any language and not just the language in which the consensus engine is written in.
