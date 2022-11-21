# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain


***
## Choose correct branch for viewing the homework
***

### h4 BitCoin intro

#### Nakamoto, Satoshi 2008: Bitcoin: A Peer-to-Peer Electronic Cash System[^crypto]

Bitcoin is a proposal for electronic transactions without relying on trust. Coins are made from digital signatures and to solve the issue of double-spending
p2p network using proof-of-work to record a public history of transactions. Therefore it becomes increasingly inconvenient / impossible for an attacker to change the chain if honest nodes control the majority of CPU power.
 
The "need" for bitcoin/cryptocurrency comes from the fact that 
> no mechanism esxists to make payments over a communications channel without a trusted party
Cash payments are trustworthy for the most part but there is always a possibility for a fraud.
 
P2P or peer-to-peer version of electronic cash was created to make it easier to avoid transactions going through financial institutions.
 
Network timestamps are hashed into an ongoing chain of hash-based proof-of-work which forms a record that cant be changed
 
This makes it so that it is computationally impractical to reverse these transactions.
 
Elctronic coin = a chain of digital signatures
Each tranfer between nodes (owners) is hashed and signed of the previous transaction and the public key of the next owners and adding these to the end of the coin.
 
To avoid double spending, transactions are public.
 
Implementing a distributed timestamp server on p2p a *proof-of-work* is required. 
It involves scanning for value that is hashed (with SHA-256 for example) the hash begins with a number of 0 bits.
The work is exponential in the number of 0 bits required.
 
**Network**
 
Network runs as follow (direct quote from the whitepaper)
- New transactions are broadcast to all nodes (owners).
- Each node collects new transactions into a block.
- Each node works on finding a difficult proof-of-work for its block.
- When a node finds a proof-of-work, it broadcasts the block to all nodes.
- Nodes accept the block only if all transactions in it are valid and not already spent.
- Nodes express their acceptance of the block by working on creating the next block in the chain, using the hash of the accepted block as the previous hash.
 

#### Felten et al 2015: Bitcoin and Cryptocurrency Technologies

Hash functions 
- take any string as input
- fixed output
- efficiently computable

As security properties:
- collision free
- hiding
- puzzle-friendly

**Collision free** 
Means that input of x and y when hashed should not have the same output. There is some collision in some cases, because there are motr possible inputs than outputs.  
But the key question is that no one should be able to find a collision. The odds of someone finding a collision is not really attainable.

Recognizing if files are the same --> simple way of doing this is to compare their hashes. If we believe to the thesis that there are very few possible collisions then this should be a surefire way of making sure that two files, strings, w/e are the same.

**Hiding**
There should be a way to hash values x ín a way that you can't really find the original input. This however is not the case because given two options for the input it is easy to reverse a hash. But if the x hash is concatenated with another values hash then the original input is truly well hidden.

**Puzzle-friendly**
If someone wanted to target the hash function if they want to come out to output y if there is part of the input that is chosen to be part of the input, then it is very hard to compute the original input value. 


#### Really black friday

Using the yahoo Finance summaries[^yahoo] it seems that on very long timeline Bitcoin has been a very succesful investment. And for many people it really has been a succesful investment. If you were one of the early adopter in 2014-2017, than you have been able to 10-20 times your investment. On the other hand if you invested all your savings around one year ago when the value was 56335 dollars... than I have bad news for you. Current price is around 15440 dollars per BTC. 

On the other hand there have been some major drops earlier in BTC history[^returns]: 2014: -58%, 2018: -73%. Overall investments are definitely positive (2011: +1473%, 2013: 5507%, 2017: 1331%), but we shall see if the road is negative from here on out. 


[^crypto]: https://bitcoin.org/bitcoin.pdf
[^yahoo]: https://finance.yahoo.com/quote/BTC-EUR?p=BTC-EUR&.tsrc=fin-srch
[^returns]: https://www.goodfinancialcents.com/bitcoin-annual-returns/