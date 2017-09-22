# Supload Technical Whitepaper

[1]
Evaluating this context in a larger diagram of any systems infrastructure, it’s obvious that our current web isn’t as privacy secure or censorship resistant as we desire. Economies of scale have allowed single institutions to offer a vast amount of processing power and storage on the internet for very low prices, thereby increasing their market share to a point where they individually control large segments of internet activity, often under the supervision of less-than-savvy governments. In a post-borders era where the Internet knows no bounds, such jurisdiction has little or no meaning.

The current internet is nowhere near as privacy secure or censorship resistant as we desire. While the first wave of internet applications have sped up the adoption of the internet by the world. We also have given away a lot of our personal privacy to these corporations. The internet has created the largest corporations in history, that control our private data, to use and share for their own benefit.

The forthcoming decentralized internet is an attempt to move our personal data and privacy out of centralized corporate data silos.

This whitepaper is an outline of how we plan to achieve a fully decentralized backend of Supload image and video hosting. The end goal is a permanent and uncensorable copy of the hosted content. All data, website state and open sourced tools to interact with this data will be freely available to public.

This documents will be separated into the main four future technical / decentralized feature upgrades.

1. **Payment Scalability -** Integration with the lightning network on the Bitcoin and Litecoin blockchains. This will facilitate near realtime micropayments to Supload users as their content is generating pageviews. Think of it as streaming payments.
2. **Permanent Decentralized Storage -** All uploads to Supload will be permanently stored in the uncensorable IPFS data network.
3. **Decentralized Computation -** Utilizing the proposed Plasma smart contract framework on the Ethereum blockchain, computation of the current website state (new posts, votes, user authorization, moderation) will be finalized on our own public blockchain. Consensus will be  miners will be rewarded with the SUP token.
4. **Decentralized Image and Video Compression -** User experience is still needs to be a priority. Heavy computation needs to be done to separate large video files into small chunks to facilitate different resolution playback depending on available bandwidth. Images need to be compressed to different resolutions to enable fast loading on slower internet connections. The golem network is a possible solution to renting cpu time from a network of users to run the neccessary computation.


## Current State of Decentralized Applications

Not all the necessary tools exist today to completely decentralize Supload. All of the tools we need are currently under development though. Thanks to the recent rise in fundraising from the initial coin offering model, the necessary protocol upgrades are being greatly expedited. The decentralized internet is coming, rapidly. ICO's have assured that. We want to be one of the first consumer applications that connects all of these protocols into a easy to use product that can achieve mass adoption.

With that said, the problems these protocol upgrades are trying to solve are extremely difficult computer science problems that have never been solved before. So putting exact completion dates on each of these features is very difficult. Here is how we see the current landscape.

![Decentralized Supload](https://i.supload.com/rygoFMFls-.png)

But since some of these advancements need to occur primarily at the protocol level, we're not seeing the rapid development that is happening around startups that are making a new token. The economic incentive is just far greater than contributing your time to advance a protocol like Ethereum. But the potential benefit that a scaling solution like Plasma or Lighting could produce is immense and neccessary. So this raises a difficult question. Where should the money to fund protocol level development come from? Private funding? Crowd funding?

That is why we're going to commit, after the successful completion of our token sale, a full time developer to helping solve the blockchain scalability problem. This roadmap relies heavily on the Plasma Ethereum framework, it only makes sense for us to contribute full time work for it's completion.

Upon full funding in our token sale, we will also commit a full time developer to helping the open source projects surrounding the blockchain ecosystem. HLS streaming of video from IPFS sources is a currently open issue on github for example. Or committing code to the wallet manufacturers with lightning network integration.

We hope this start a new trend in tokenized applications. If you are a well funded startup relying on future protocol and open source products, hire full time developers to help speed up the future decentralized web.



## 1.0 Payment Scalability

With a low threshold of allowing users to withdraw their bitcoin earnings after earning only $1.00 USD, we need to think to the future about how to scale these payments. With sufficient growth, Supload could potentially spam the bitcoin blockchain with many low $1.00 transactions.

Users are currently incentivized to withdraw their earnings as soon as they reach the $1.00 minimum withdraw threshold. Anything else is entrusting a 3rd party(Supload) to hold their earnings until they withdraw. Entrusting a third party to hold you coins is bad cryptocurrency security.

The solution is to move these payments off the primary bitcoin blockchain, onto a secondary payment channel. We can update this payment channel as often as we like. The end user can then close the channel whenever they want, publishing the final transaction to bitcoin blockchain. Finalizing the transaction between Supload and the user. With no risk to the payee at any point.

### 1.1 :zap: Lightning Network

The Lightning Network allows us to stream payments to our users. The lightning network makes it so Supload can pay users every ten minutes when our analytics have finished running.

The Lightning Network makes it so we can transact very small amounts of bitcoin in near realtime, for very little fees. This will be a feature that is available to the highest ranked users on Supload. A few of our biggest content creators are responsible for a majority of the payments.

The lightning network will provide an extra layer of trust for users. As the payments are being updated, the payee is receiving a new signed Hashed Timelock Contracts from Supload. With the committed amount of payment. At that point, it's impossible for the payer (Supload) to go back on the agreed upon payment amount. The funds are then being held in a contract on the bitcoin blockchain.

The amount owed to the content creator will update every 10 minutes when we run our analytics, adjusting for pageviews in that period of time.

When the user wants to finalize and receive their funds, they can close the payment channel with Supload. The users wallet will the take the most current Timelock Contact and publish it to the bitcoin blockchain. Only one transaction hits the bitcoin blockchain.

While the payment channel is open, the user is at no risk of not receiving their funds and wanting to withdraw after every $1 is accrued.

### 1.2 Unidirectional Payment channels
The payment channel consists of two on chain transactions. Supload creates the payment channel by sending funds into a bitcoin multisig address.

Both Supload and the payee party will agree to enter into a off-chain payment channel.

The initial payment channel is funded by Supload into a 2 of 2 multisignature address.

The payee is free to redeem funds whenever they are happy with the payment.

![Image of Supload HTLC](https://i.supload.com/Hkl15gj35b.png)




## 2.0 Permanent Decentralized File Storage

Moving the backend storage to the IPFS filesystem allows any uploaded content to Supload to be insured to be available for the rest of time. IPFS is censorship proof file storage that is guaranteed to exist as long as the internet is working.

* **User Benefits -** Video and Image hosting sites are notoriously prone to shutting down or having to censor content due to pressure from governments or advertisers. Whether it is legal pressure for the content they are hosting, or the costs of operation become unbearable.
* **Message Board Benefits -** When a content hosting site goes down, the links to that content are still spread throughout the internet. Broken image links is a longstanding problem for message boards and content aggregation sites such as Reddit. Forcing most moderators to only accept links to one to two of the most trusted centralized hosts. But no website can guarantee to be around forever.

### 2.1 Data Resolution
Content on IPFS is addressed by a cryptographic hash of the content of the file. IPFS then uses it's own location resolution system built on a Distributed Hash Table. It's much more efficient than the current IPv4 location based system the internet uses. It's quite revolutionary to think of data storage not as, where in the world is the server located that has this data, but rather, who in the world has the file with these contents.

### 2.2 Fetching content if Supload.com does not resolve
The current state of Supload will be freely available on an Ethereum sub blockchain. Resolving the hash for the content from a Supload URL, will only require communicating with a fully synced Ethereum wallet.
#```https://www.supload.com/<ipfshash1>```

### 2.3 Efficiency of data deduplication in IPFS
IPFS addresses content based on the hash of the objects contents, not by it's location. Duplication of the same images and videos will result in only one copy being stored. This is an extremely efficient method for video and image storage. Duplicate posts of the same data will result in pointing to one copy of the file since the resulting base58 hash will be identical.








## 3.0 Decentralized state computation
The final step in complete decentralization of Supload, is removing the need to have servers at all.

The current state of Supload needs to be removed out of a centralized database, and into a public blockchain.

### 3.1 IPFS Storage of state database
IPFS is ideal to use as a database to store the current state of the site. The ability to de-duplicate data works in Suploads favor, since most state updates only change on the newest most popular uploads.

The totality of IPFS objects forms a cryptographically authenticated data structure known as a Merkle DAG (Directed Acyclic Graph).

This is one of the most exciting use cases for IPFS. A blockchain has a natural DAG structure in that past blocks are always linked by their hash from later ones.

All that needs to be stored then in the Supload blockchain is a hash pointing to the current state of Supload in IPFS.

The current hash in the block header in the Supload blockchain will reference the base58 hash of the state files in IPFS. Since the final source of truth for our SUP blockchain is on the Ethereum blockchain, anyone with a fully synced Ethereum wallet will be able to access the newest state files in IPFS.

### Blockchains in IPFS
The DAG structure found in blockchains can be easily replicated in IPFS. Past blocks can always be linked by their hash from later ones. The state database that Ethereum uses, can be modeled in IPFS. So storing the current state of Supload can follow the same state model.

Every block in the Supload chain will have a merkleized trie of the current state, a merkle tree of transactions, and a reference to the prior state being modified. Using IPFS to store the state and transaction trees will allow miners to only store small set of data on chain. The deduplication we gain on IPFS can be seen below. Only the state entries that have changed between two blocks will need to be stored.

![State database in IPFS](https://i.supload.com/S1xZdzGXiW.png)


### 3.2 Plasma Ethereum Framework
Presently every Ethereum miner has to independently replicate each smart contract action in its entirety, whereas TrueBit outsources most computation work to a handful of entities. In this way, TrueBit makes secure computing affordable. [TrueBit Whitepaper]

Ethereum’s variable gasLimit restricts the number of computation steps that smart contracts can perform.[]

Participants are rational in the sense that they act to maximize their
individual profits. In particular, we expect that CPUs will show up to
do computational tasks if and only if they expect fair compensation
for their work.


Decentralized Applications can be reframed as a MapReduce problem with economic incentives for correct activity bonded by the Sup token.[Plasma whitepaper]

This is primarily about data storage (CRUD). Primarily computation and proofs are around
access control, identity (votes and posts), and moderation. Many web applications are
actually just doing CRUD on the back end. [Plasma whitepaper]


Plasma is a framework of contracts, to enable massive scaling and computation on the Ethereum blockchain. We see this as a way to handle the validation of the state of the site in a blockchain.

Plasma is a proposed smart contract to the Ethereum network by Joseph Poon and Vitalik Buterin. Plasma is a series of contracts which runs on top of main Ethereum blockchain. The root network contract process only very small amount of commitment from child Blockchain which can do a huge number of computations.

The special things is that all commitment are broadcasted periodically on the root Blockchain time to time from the child.

Commitments are broadcasted periodically to the root blockchain from the child Plasma chains. Only a tiny amount of commitments is needed for the entire computation of Supload.




### 3.3 Blockchains in Blockchains






## 4.0 Decentralized Image and Video Compression

The computation needed for image and video Compression is extremely CPU intensive. For the future full length video update to Supload, video files need to be compressed to multiple resolutions (360p, 540p, 720p) to enable a smooth browsing experience depending on users bandwidth. Those different resolution files then need to be split into short one second chunks, to be able to facilitate smooth switching of resolutions depending on deteriating or improving network conditions.

The golem network[5] offers renting out idle CPU cycles from it's network of users. Docker[] images with binaries for compression and chunking can be uploaded to their Application Registry. Golem network users can reference data stored in IPFS. Run the necessary computation for compression, and upload the finished product back into IPFS.

### 4.1 Docker images preloaded with FFMPEG





## 5.0 Decentralization
The end goal of supload is to completely decentralize the storage and computation of the current state of the site. This will create a public, uncensorable network. The current state of the site (comments, votes, titles, descriptions) will be held in a publicly accessible blockchain based on the forthcoming Plasma smart contract Ethereum framework.

![Image of current infrastructure](https://i.supload.com/rJgg6LixjZ.png)

The goal is to decentralize the backend, allowing anyone to be able to build frontends to our content. Opening the backend will give developers the ability to create apps and website frontends to our content. They are free to monetize any way they see fit.

This will ensure the long term survival of our blockchain and product. Giving developers access to our backend is giving them access to an already built and thriving community. No longer having to worry about building a product, then getting a user base and building a community. They are free to focus on the interface to our content only. This is in effect, crowdsourcing the user interface.

### 5.1 Crowdsourcing User Interfaces
While a single company like Supload may never be able to build the best possible frontend to our content. Opening up the backend will allow rapid experimentation of interfaces by developers. Websites and apps that would normally be our competitor, now strengthen our core product. We will never be able to predict what this perfect interface could look like.

![Image of decentralized infrastructure](https://i.supload.com/r1xZ28olob.png)

### 5.2 User Interface Incentive




## 6.0 SUP Token Utility
The safety mechanism in Pulse blockchains is chain halting if bad actors are found on the network. The easiest way to handle a bad miner, is not to try to convince the miner to act nicely, but for everyone to drop out of the chain all together.

This works much in the same way as the Nakimoto consensus.

### 6.1 Token Bonding
The primary purpose of the SUP token is the reward to miners to compute the current state of the site. If our tokens primary value is derived from this reward, miners are financially incentivized to not attack the chain. If the chain halts, the value of the chain declines, effecting the economic price of the SUP token. Creating significant economic incentive for continued operation.

This makes the SUP token far more effective in protecting the Supload chain than any other currency. If we were to bond the chain with Ethereum or Bitcoin, chain halting will have no effect on the economic price.



## 7.0 Acknowledgements
Taylor Gerring - https://blog.ethereum.org/2014/08/18/building-decentralized-web/

IPFS block storage discussion - https://www.reddit.com/r/ethereum/comments/44qpks/what_would_be_needed_to_store_the_blockchain_as_a/czs5qnh/

Consensys, Introducing IPFS - https://medium.com/@ConsenSys/an-introduction-to-ipfs-9bba4860abd0

IPFS whitepaper - https://ipfs.io/ipfs/QmR7GSQM93Cx5eAg6a6yRzNde1FQv7uL6X1o4k7zrJa3LX/ipfs.draft3.pdf

Plasma whitepaper - http://plasma.io/plasma.pdf

Filecoin whitepaper - https://filecoin.io/filecoin.pdf

Golem Network - http://golemproject.net/doc/DraftGolemProjectWhitepaper.pdf

Ethereum Research Fraud Proofs - https://github.com/ethereum/research/wiki/A-note-on-data-availability-and-erasure-coding

Ethereum Trie JS code - https://github.com/ethereumjs/merkle-patricia-tree

Understanding the Ehereum Trie - https://easythereentropy.wordpress.com/2014/06/04/understanding-the-ethereum-trie/
