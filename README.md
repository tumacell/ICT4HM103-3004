# ICT4HM103-3004
School course repo: ICT Security Basics from Trust to Blockchain


***
## Choose correct branch for viewing the homework
***

### h4 BitCoin intro

#### Nakamoto, Satoshi 2008: Bitcoin: A Peer-to-Peer Electronic Cash System[^crypto]

*Bitcoin is a proposal for electronic transactions without relying on trust. Coins are made from digital signatures and to solve the issue of double-spending Bitcoin uses p2p network and public transactions. It also uses proof-of-work to record a public history of transactions. Because of these reasons it becomes increasingly inconvenient / impossible for an attacker to change the chain if honest nodes control the majority of CPU power. The public nature of transactions, the way the network works, the distributed nature of it all.. makes BTC a very safe alternative for digital transactions.*
 
The "need" for bitcoin/cryptocurrency comes from the fact that 

> no mechanism exists to make payments over a communications channel without a trusted party

Cash payments are trustworthy for the most part but there is always a possibility for a fraud when using the "traditional" ways for payment.
 
P2P or peer-to-peer version of electronic cash was created to make it easier to avoid transactions going through financial institutions.
 
Network timestamps are hashed into an ongoing chain of hash-based proof-of-work which forms a record that cant be changed. This makes it so that it is computationally impractical to reverse these transactions. If an adversarial hacker tries to alter some element of the blockchain, it will be noticed because the public transactions will not work correctly (the hash values dont make sense).
 
Elctronic coin like Bitcoin is basically a chain of digital signatures. And each tranfer between nodes (owners) is hashed and signed to the previous transaction and the public key of the next owners and adding these to the end of the coin.
 
Bitcoin network runs as follow (direct quote from the whitepaper)
- New transactions are broadcast to all nodes (owners).
- Each node collects new transactions into a block.
- Each node works on finding a difficult proof-of-work for its block.
- When a node finds a proof-of-work, it broadcasts the block to all nodes.
- Nodes accept the block only if all transactions in it are valid and not already spent.
- Nodes express their acceptance of the block by working on creating the next block in the chain, using the hash of the accepted block as the previous hash.
 
#### Felten et al 2015: Bitcoin and Cryptocurrency Technologies[^coursera]

**Hash functions**

- take any string as input
- fixed output
- efficiently computable

As security properties:
- collision free
- hiding
- puzzle-friendly

*Collision free* 

Means that input of x and y when hashed should not have the same output. There is some collision in some cases, because there are more possible inputs than outputs. But the key question is that no one should be able to find a collisions. The odds of someone finding a collision is not really attainable.

Recognizing if files are the same --> simple way of doing this is to compare their hashes. If we believe to the thesis that there are very few possible collisions then this should be a surefire way of making sure that two files, strings, w/e are the same. Collision free is a key factor in blockchain technologies.

*Hiding*

There should be a way to hash values x ín a way that you can't really find the original input. This however is not the case because given two options for the input it is easy to reverse a hash. But if the x hash is concatenated with another value's hash then the original input is truly well hidden.

*Puzzle-friendly*

It is extremely hard for someone to come up with a correct input value of the hash based on the output value. For example if I know the output to be Y then if the original value X is hashed with another value K, than my chances of ever finding out the X is extremely low. Even if I knew the output Y.

**Hash pointers**

Hash pointer is a point where information is stored and also hash of the info. With that pointer one can verify that the included information has not changed. Hash pointers are also there for security. If an adversary wants to attack a blockchain, they will need to change the hash pointers all the way to match the hash values --> simple data change at the low-level will influnece the whole chain.

**Digital Signatures**

Digital form signature which can only be made by the author, but anyone can verify it. It is document related and cannot be copied to another document since it also implies that YOU are authorizing that particular piece of document.
Three parts for digital signatures:
- Generate keys (keysize) (secret key for signing, public key for verification)
- Sign (secret key, document / message that is signed)
- Verify (public key, message, signature)

**Public Keys as Identities**

Public keys can  be used as identity since you are the only one who knows the secret key. 
In a decentralized identity management anyone can make identities any time they want and there is no centralized oversight of identities.
Also known as "addresses" in BTC.

#### Really black friday

Using the Yahoo Finance summaries[^yahoo] it seems that on a very long timeline Bitcoin has been a very succesful investment to the lucky ones. And for many people it really has been a succesful investment. If you were one of the early adopters in 2014-2017, than you have been able to 10-20 times your investment, possibly even more. On the other hand if you invested all your savings around one year ago when the value was 56335 dollars... than I have bad news for you. Current price is around 15440 dollars per BTC and the current trend is down. 

On the other hand there have been some major drops earlier in BTC history[^returns]: 2014: -58%, 2018: -73%. Overall investments are definitely positive (2011: +1473%, 2013: 5507%, 2017: 1331%), but we shall see if the road is negative from here on out. 

#### Not BitCoin[^kryptofi]

Altcoins are basically any other cryptocurrency other than Bitcoin (BTC). The term comes from "alternative coin".
There are a number of different altcoins like Ethereum, dogecoin and cardano for example.

**Ethereum**[^ethereum]

Ethereum is the best known and has been most popular altcoin and a "competitor" for Bitcoin. 
Ethereum as a cryptocurrency is a bit more versatile than Bitcoin and many other tokens or coins have been built on top of Ethereum network. It is an ecosystem for nearly 90% of other tokens (Chainlink, Aave and so on) and more comparable for an operating system. It is also a platform where you can build distributed applications (dApps) and smart contracts[^ethereum]. 

The criticism against Ethereum has been that it uses a lot of energy when mining and also when using transactions.

**Dogecoin**[^doge]

A memecoin made as a joke and first published in Reddit forums around 2013. It is perhaps best known for being pumped up in value by Elon Musk. The idea behind the Dogecoin is that it would be an independent and "fun" payment method. The coin icon is a shiba inu dog.

There were many fast moving valuations where the value of the coin went up ~300% in couple of days and then came down 50% in one single slash the next day.

Dogecoin is not better (or worse?) than Bitcoin and it really does not have any particular value or purpose, other than being a memecoin or a joke.

#### What's a block chain?[^blockchain],[^blockchain2]

Blockchain is a system that records any sort of information in a way that makes it extremely hard / impossible to change, hack or cheat the blockchain. It is also known as distributed ledger technology[^blockchain].

You can think of blockchain through a more everyday example such as Google Docs. When you create a Google Docs and share it with other collaborators the document is not copied with each participant, rather it is distributed. Decentralized distribution chain gives access to participants at the same time so they can alter the document. All the changes and modifications are recorded at the same time and in a transparent way. As a difference to Google Docs though, original data on the blockchain can't be modified.

The decentralization of digital assets allows for real-time access. All the changes are documented which in itseld preserves integrity and trust. 
Each block in the blockchain includes the data (in cryptocurrencies for example the transaction information), the hash (all of the content, if something is changed in the data -> hash changes) and hash of the previous block (creates a chain of blocks)[^blockchain2].

The security aspects are the chain mechanism (if you tamper with one block, you have to make sure it is followed up with the following blocks) and the distributed nature (p2p network).



[^crypto]: https://bitcoin.org/bitcoin.pdf
[^yahoo]: https://finance.yahoo.com/quote/BTC-EUR?p=BTC-EUR&.tsrc=fin-srch
[^returns]: https://www.goodfinancialcents.com/bitcoin-annual-returns/
[^kryptofi]: https://kryptovaluutta.io/mika-on-altcoin/
[^ethereum]: https://virtuaalivaluutta.com/ethereum/
[^doge]: https://virtuaalivaluutta.com/dogecoin/
[^blockchain]: https://terokarvinen.com/2022/trust-to-blockchain-2022-autumn/
[^blockchain2]: https://builtin.com/blockchain
[^coursera]: https://www.coursera.org/learn/cryptocurrency/home/week/1