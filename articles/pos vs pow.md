https://medium.com/coinmonks/proof-of-work-vs-proof-of-stake-for-real-idiots-a23ac4565649

# The article talks about consensus algorithms and POW vs POS vs others

POW/POS/... + other rules = consensus algorithm

POW + longest chain rule = nakamoto consensus = bitcoin consensus algo
Blockchain -> very old -> used by surety -> hashes stored in chains and published in newspaper regularly.
POW -> present earlier, called hashcash, making sending emails costly reducing spams by solving cryptographic hash before emailing
Two problems basically:
1. How is it assured that network doesn't get flooded?
2. How they agree on conflicts?

WRT bitcoin, first problem solved by hashcash, and second is by longest chain rule.
In bitcoin, the number of users using the network scales very well, but the number of transactions they make is not scalable.
A great example is restraunt with infinite tables, but only fixed number of orders.
The mismatch between active user scaling and passive user scaling is bad. Some solutions are there, such as lightning network, when multiple restraunts are open, instead of only tables who then request for orders.

Though, going back to the issue of sorting. Bubble sort has a time complexity of **O(nxn)**, quick sort has a time complexity of **O(nlogn)**, while sleepsort has time complexity of O(n) theoritically. Here, we spawn single process for each step, which in turn loops n times, since it is parallel. Though, this is to good to be true because it takes time for a subprocess to spawn. Also, this doesn't work exactly as expected, because it doesn't care about the computational complexity of each subprocess.

Referring back to bitcoin, it is obvious that the infinite scaling of sleepsort helps. Thus, this means that infinite number of miners can search for a block parallely as the number of miners increase, but this doesn't mean infinite number of transactions can be processed. The number of transactions can not be increased by a lot. We have to wait until a block is found and the blocktime can not be reduced like sleepsort. Reduccing the time too much subprocess spawn time dominates with no sorting. ie in bitcoin, if blocktime is low, the computation is so fast, that the network communication dominates and the finder of previous block has more chance of finding the following block. Thus, the nakamoto consensus won't work.

Another similarity exists between BFT consensus(BFT with dPoS) and bubble sort. This kind of gives O(nxn) behavior.
Infinite scaling in bitcoin is for passive users(readers/miners). For active users, BFT has lot more scaling to offer.
In fact, there is something called Proof of Authority that users can follow instead, though the problem with PoA is it is highly permissioned.
The permissionless quality of PoS is bit lesser than PoW, because one counter case is that in PoS, you can not enter the market if everybody has decided not to sell you any coins. Thus, the technology is permissionless, but it can still prevent you to enter the market in adverse conditions. Though, this also implies that it is comparatively easier to attack a bitcoin PoW network but difficult to attack the PoS network, sincce you will need to get a 67% control of the network in that case.

In fact, this is where CAP theorm comes into picture. CAP refers to Consistency(C), Availability(A) or Partition Tolerance(P). The theorn states that either 2 of them is strong, or 1 is strongest at the expense of the other.
The more participants can be handled the higher the availability. PoS wins vs. PoW. Permissionlessness has a lot to do with partition tolerance. Is it possible to fill the gaps if half of the network is gone? Can the network even continue if too many participants break away? PoW wins vs. PoS. To be precise this is the killer feature of Nakamoto Consensus. It works if all but one node go offline. It works if there is a nuke creating an EMP wave shutting down half the globe electronically. After the nodes come back online they can join the network, see if the others have found some blocks.

Thus, PoW wins at partition tolerance while PoS wins at availability.
The next part is consistency. This means that there is a single reality that everyone knows and agrees with. There can be forks in the blockchain, and there can be concurrent blocks such that one chain is omitted in the favor of another. In PoS, this is not a problem because consistency is very high due to the fact that there is a single source of truth at the end, and if 2-3 validators agree on a set of blocks they are final.
[INTERESTING POINT: IOTA doesn't have longest chain rule. It gives up consistency to solve the issue of availability]
Thus, PoS with fast finality comes with high consistency. The drawback is that the chains halt if too many validator nodes don't come online.
**Thus, it can be understood that every consensus algorithm comes with its own sets of drawbacks and advantages. For nakamoto consensus, the advantage is P and C, but drawback is A. For delegated PoS, the advantage is C and A, but drawback is P.**

Based upon the above points, it can be proved that bitcoin is not a good method of making payments, as consistency and availability are the 2 major issues for good payment services, and while bitcoin is good for consistency, it is not good for availability. The reason for higher valuation is not because of its use case, but because of people's perception of the bitcoin. **Or is it?**. But, the value of currency is also decided based upon the fact that it is a store of value.

For the store of value to be good, you don't need high value. What you need instead is high partition tolerance and high security. Also, consistency is also not that much of an important factor. This is similar to gold obviously. Gold is bad at A and C, but great at P. 

Though, this doesn't by default give PoS the crown, because while nakamoto consensus is not good wrt transaction of value, and only store of value, the IOTA consensus provides a method of great A and P, but bad C, and works on PoW. 
In practice there is a coordinator. PoS and PoW can not be used interchangeably. Thus, they have to be taken in tandem. **BFT PoS with fast finality** is great for transaction of value, but **Nakamoto consensus** is great for store of value.
People might say gold standard should not have been avoided. But, it doesn't make sense to use gold to make payment for my train ticket. Also, our fiat system is not based on coins but is rather electronic money credit system. This provides it a better design space. When it comes to decentralization, PoS provides a wider design space, but with its own limitations.

For nakamoto consensus, the PoW problem doesn't exist, because there is a single chain, and it will take double effort to solve blocks for a fork(there can be haard forks though). On the other hand, in case of fiat, such dubious behaviors need to be punished  as is the case. Also, 51% attack(67% in case of BFT PoS) should not make sense.
