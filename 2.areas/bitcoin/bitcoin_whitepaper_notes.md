[HELL MONEY PODCAST](https://www.youtube.com/watch?v=cdJWVApjeFc&ab_channel=HellMoneyPodcast) 

## cypher punk mailing list 2008

enthusiasts in privacy and p2p internet , sharing new innovations in tech + cryptography . 
satoshi shares PDF to that mailing list on halloween 2008.

1. Release of Whitepaper (2008)
2. Release of Software + Sourcecode
3. Genesis Block Code (January 3 2009)

[[bitcoin_whitepaper.pdf]]
written like an academic paper

## political and social context

concerns about privacy
how to take power away from institutions (data + censor wise)
critique of FIAT + avoiding centralized authorities

first message on BITCOIN
	"The Times : Chancellor on the brink of Second Bailout for Banks"


## Intro

Bitcoin Itself is A-Political

Satoshi is not CEO
BITCOIN is not a COMPANY

You can read more comments by satoshi here
[bitcointalkforum](https://bitcointalk.org/) 


## 2. Transactions

Electronic Coin = A chain of Digital Signatures

1. Previous TX + Owner2PuK (public key) create HASH
2. HASH is signed by Owner1 PrK (private key)
3. Repeat

With just this , there is no way to verify if user double spent . who verifies this information and who decides what is the canonical order of TXs ?

## 3. Timestamp server

Solution to double spend starts with Timestamp Server.
Just like the hash is created for TXs there is a hash created for the complete Block of TXs

1. taking hash of a block to be timestamped and widely publishing the hash .
2. timestamp proves that data must have existed at that time . 
3. each timestamp includes the previous timestamp in its hash , forming a chain .


## 4.  Proof-oof-Work

To create a distributed timestamp server on a peer-to-peer basis , you need a proof-of-work system . Proof-of-Work involves scanning for a value that when hashed , hash begins with a number of zero bits (ex. 00101100) . Avg work required is exponential in the number of zero bits . Once the Computer effort has been expended to satisfy PoW , the block cannot be changed without redoing the work . 

Instead of 1IP-1vote 1CPU=1vote

To attack , malicious CPUs would have to redo all of the work done by the honest CPUs.
To compensate for increasing hardware speed and varying interest in running nodes over time , PoW difficulty is determined by a moving average targeting an average number of blocks per hour . If blocks generate too fast , difficulty increases . 


## 5. Network

Steps to run the network :
1. new TXs are broadcast to all nodes
2. Each node collects new TXs into a block
3. Each node works on finding a difficult PoW for its block
4. When node finds a PoW , it broadcasts to all nodes
5. Nodes accept the block if all TXs in it are valid and not already spent
6. Nodes express their acceptance of the block by working on creating the next block in the chain , using the hash of the accepted block as the previous hash

Nodes always consider the longest chain to be the correct one and will keep working on extending it . If two nodes broadcast different versions of the next block simultaneously , some nodes may receive on or the other first . In that case , they work on the first received but save the other in case it becomes longer . The tie will be broken when the next PoW is found and one becomes longer ; nodes working on previous will switch to the longest . 

## 6. Incentive

By convention , the first TX in a block is a special TX that starts a new coin owned by the creator of the block . This adds incentive for nodes to support the network + provides a way to initially distribute coins into circulation , since there is no central authority to issue them . 

Once a predetermined number of coins have entered circulation , the incentive can transition entirely to transaction fees and be completely inflation free . 

Nodes that are doing PoW the node that created the new block , creates a prize of BTC for itself (depends on what period we are on) .


## 7. Reclaiming Disk Space

Once latest TX in a coin is buried under enough blocks , the spent TXs before it can be discarded to save disk space . To facilitate wo breaking the block's hash TXs are hashed in a Merkle Tree with only the root included in the block's hash . Old blocks can then be compacted by stubbing off branches off the tree . Interior hashes do not need to be stored .

Block Header (Block Hash) with no transactions would be about 80bytes . If we suppose blocks are generated every 10 minutes , that would be 4.2MB per year . 


## 8. Simplified Payment Verification

If you dont own a full node you cannot verify a TX for himself but if you can link it to a place in the chain , he can see that a network node has accepted it and blocks were added after it , confirming the network accepted the TX . 

Businesses that receive frequent payments will probably still want to run their own nodes for more independent security and quicker verification . 


## 9. Combining and Splitting Value

Each TX has Inputs and Outputs . 

you dont have a balance , rather you have different coins of different values . for example you have 10 BTC but totaled by 7BTC 2BTC 1BTC , for you to pay 5BTC you would use your 7BTC (input) , the TX would destroy your 7BTC (input) "coin" create a 5 BTC (output) . this first output goes to pay for 5BTC and the second output would be 2BTC to yourself . your address would hold 2BTC + 2BTC + 1BTC separately . 


## 10. Privacy

The traditional banking model achieves a level of privacy by limiting access to information . Privacy can be maintained by breaking the flow of information in another place : by keeping public keys anonymous . The public can see all TXs but cant link people to public keys . 

As additional firewall , a new key pair should be used for each transaction to keep them from being linked to a common owner . Some linking is still unavoidable with multi input TXs . Which necessarily reveal that their inputs were owned by the same owner . 


## 11. Calculations 

