# Bitcoin notes:

### Abstract:

P2P electronic cash to allow online payments to be sent directly from one party to another without any intermediary. Digital signatures important, but major game is wrt the double spending problem which is usually handled by third party.
Network timestamps transactions are hashed into an ongoing chain of hash-based proof of work. Longest chain contains the proof of longest sequence of events, and maximum pool of CPU power.

### Introduction:

Commerce based on 3rd party(financial institutions) trust. System suffers from inherent weaknesses of trust based model. Completely non-reversible transactions are not possible since financial institutions can not avoid mediating disputes. Cost of mediation increases transaction costs, limiting possibilities of micro transactions and putting limit on minimum transaction size. Secondly, there is extra effort wrt more info required for merchants/customers for making the transaction.
Electronic payment systems based on cryptographic proof instead of trust, allowing willing parties to make payments without need of 3rd party. Computationally irreversible transactions would protect sellers from fraud, and help in escrow mechanisms.

### Transactions:

Electronic coin -> chain of digital signatures. Owner transfers the coin to next by digitally signing a hash of previous transaction and public key of next owner adding these to next chain. Payee verifies the signatures to verify the chain of ownership. Problem is payee can not verify that one of the owners did not double spend the coin. In our case, the first transaction is the final transaction, and thus, double spend cases don't happen. Only way to be aware of absence of transaction is to be aware of all the transactions.

### Timestamp Server:

Timestamp server works by taking a hash of a block of items to be timestampped and widely publishing its hash. The timestamp proves that data exists in time, and each timestamp of a hash includes the timestamp of the previous hash, thus forming a chain.

### Proof of work:

Distributed timestamp server on a P2P basis, proof of work similar to hashcash. The hash begins with a number of 0 bits.Average work required is exponential of the zero bits required. Once CPU power is expended to satisfy proof of work, the block can not be discarded without redoing the work. PoW is one CPU one vote. Majority decision taken by longest chain. If majority of CPU power is controlled by honest nodes, honest chain will grow the fastest, and outpace any competing chains. To compensate for increasing hardware speed and varying interests in running nodes over time, POW difficulty is determined by moving average targeting an average number of blocks per hour.

### Network:

Steps to run a new network are:
1. New transactions are broadcast to all nodes.
2. Each node collects new transactions into a block.
3. Each node works on finding a difficult proof of work for its block.
4. When node finds POW, it broadcasts it to the all nodes.
5. Nodes accept the block only if all transactions in it are valid, and not already spent.
6. Nodes express their acceptance is by working the next block in the chain, using hashof the accepted block of the previous hash.

Nodes consider the longest chain as the correct one, and keep working to extend it.If 2 nodes broadcast different versions of the next block, some nodes may receive one or the other first. They start working on the first one received, but save the other one if it is longer.
New transactions are not always broadcasted to all nodes.If they reach many nodes, they are poised to be picked up by one or the other block

### Incentive:

First transaction is a special transaction that starts a new coin owned by the creator of the block. Steady amount of addition of coins is similar to how miners accumulate gold. Incentive funded by transaction fees. If output of transaaction is less than input value, difference in transaction fee is added to the incentive value of the block containing the transaction. The incentive may help encourage nodes to stay honest.

### Reclaiming Disk Space:

Once latest transaction is buried under enough blocks, the spent transactions can be discarded. Thus, the transactions are included in the merkel tree with only the root included in the tree.

### Simplified Payment Verification:

User only needs to keep a copy of block headers of the largest POW chain. He can't check the transaction for himself but by linking it to a place in the chain, he can see that the network node has accepted it, and further blocks added confirm it. Though the verification is reliable as long as honest nodes control the network, and is vulnerable if the network is attacked by an attacker.

### Combining and Splitting Value:

Transactions contain multiple inputs and outputs. Normally, there will be a single input from a larger previous transaction or multiple inputs containing smaller amounts, and atmost 2 outputs, one for the payment and one for returning the change.

### Privacy:

Traditional banking model handles privacy by limiting access to info to parties involved via 3rd party. 
Privacy is handled in the bitcoin model by controlling the public access of the public keys of users. Thus, privacy is maintained by controlling the flow of information in another place by keeping the public keys anonymous. This is similar to stock markets, where the transactions are made public without revealing the parties involved in the transactions.

### Calculations:

Ignored for now!!!

