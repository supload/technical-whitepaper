# Supload Technical Whitepaper

The current Internet is nowhere near as privacy secure or censorship resistant as we desire. Centralized internet services have found ways to profit from our personal data, allowing them to offer their products for free. This has effectively kickstarted the global adoption of the internet.

In recent years, we have begun to see the shortcomings of this model. Corporate data silos are treasure troves for hackers, and we have no choice but to trust these institutions to effectively protect their networks. Furthermore, a single corporation is always susceptible to censorship from governments and advertisers.

The coming decentralized internet is an attempt to move our personal data and privacy out of centralized institutions, giving the power back to us.

This whitepaper is an outline on how we plan to achieve a fully decentralized and serverless backend for the Supload image and video hosting service. The end goal is a permanent, public, and uncensorable copy of all our hosted content. All images, videos, website states, and tools to interact with this data will be freely available to the public.

This document is separated into the four main decentralized features needed to achieve our vision.

1. **Payment Scalability -** Integration with the Lightning Network on the Bitcoin and Litecoin blockchains. This will facilitate near realtime micropayments to Supload users as their content is generating pageviews. Think of it as streaming payments.
2. **Permanent Decentralized Storage -** All uploads to Supload will be permanently stored in the uncensorable IPFS data network. Your images and videos can never be removed.
3. **Decentralized Computation -** Utilizing the proposed Plasma smart contract framework on the Ethereum blockchain, computation of the current website state (new posts, votes, user authorization, moderation) will be available on our own public blockchain. Computation by miners will be rewarded with the SUP token.
4. **Decentralized Image and Video Compression -** User experience still needs to be a priority. Heavy computation needs to be done to separate large video files into small chunks to facilitate different resolution playback depending on available bandwidth. Images need to be compressed to different resolutions to enable fast loading on slower internet connections and smaller mobile screens. The Golem Project is a possible solution to renting CPU time from a network of users to run the necessary computation.



## Current State of Decentralized Applications

Not all the necessary applications exist today to completely decentralize Supload. Fortunately, everything we need is currently under development. Thanks to the recent rise in fundraising from the Initial Coin Offering fundraising model, the speed at which the necessary applications are being built has been greatly expedited. The decentralized internet is coming quickly. ICO's have assured that. Supload aims to be one of the first fully decentralized consumer applications. We believe by achieving mass adoption of this easy-to-use product, we can not only promote mass adoption of the technology we use, but also the benefits of decentralization.

With that said, the problems these applications are trying to solve are extremely difficult computer science problems that have never been solved before. So putting exact completion dates on each of these features is very difficult. Here is how we see the current landscape.

![Current State of Decentralized Applications](https://i.supload.com/rygoFMFls-.png)

Unfortunately, the biggest and most important feature, Plasma, needs to occur primarily at the protocol level. We're just not seeing the rapid development on the protocol level that is happening with startup applications that are creating a new token to sell for funding. The economic incentive is just far greater than contributing your time to advance a protocol like Ethereum. But the potential benefit that a scaling solution like Plasma or Lighting could produce is immense and necessary. So this raises a difficult question. Where should the money to fund protocol level development come from? Private funding? Crowd funding?

That is why we're going to commit, after the successful completion of our token sale, a full time developer to helping solve the blockchain scalability problem. This roadmap relies heavily on the Plasma Ethereum framework, it only makes sense for us to contribute full time work for it's completion.

Upon full funding in our token sale, we will also commit a full time developer to helping the open source projects surrounding the blockchain ecosystem. HLS streaming of video from IPFS sources is a currently open issue on github for example. Or committing code to the wallet manufacturers to help with Lightning Network integration.

We hope this starts a new trend in tokenized applications. If you are a well funded startup relying on future protocol and open source products, hire full time developers to help speed up the future decentralized web.



## 1.0 Payment Scalability

With a low threshold of allowing users to withdraw their Bitcoin earnings after earning only $1.00 USD, we need to think to the future about how to scale these payments. With sufficient growth, Supload could potentially spam the Bitcoin blockchain with many low $1.00 transactions.

Users are currently incentivized to withdraw their earnings as soon as they reach the $1.00 minimum withdraw threshold. Anything else is putting trust in a 3rd party(Supload) to hold their earnings until they withdraw. Entrusting a third party to hold your coins is bad cryptocurrency security practice.

The solution is to move these payments off of the primary Bitcoin blockchain, onto a secondary payment channel. We can update this payment channel as often as we like. The end user can then close the channel whenever they want, publishing the final transaction to the Bitcoin blockchain. Finalizing the transaction between Supload and the user. With no risk to the payee at any point.

### 1.1 :zap: Lightning Network

The Lightning Network allows us to stream payments to our users. Lightning allows Supload the ability to pay users every ten minutes when our analytics have finished running.

The Lightning Network gives us the unprecedented ability to transact very small amounts of Bitcoin in near realtime,  for very little fees. This will be a feature that is available to the highest ranked users on Supload. A few of our biggest content creators are responsible for a majority of the payments.

The Lightning Network will provide an extra layer of trust for users. As the payments are being updated, the payee is receiving a new signed Hashed Timelock Contract from Supload. With the committed amount of payment. At that point, it's impossible for the payer (Supload) to go back on the agreed upon payment amount. The funds are then being held in a contract on the Bitcoin blockchain.

The amount owed to the content creator will update every 10 minutes when we run our analytics, adjusting for pageviews in that period of time.

When the user wants to finalize and receive their funds, they can close the payment channel with Supload. The users wallet will the take the most current Timelock Contact and publish it to the Bitcoin blockchain. Only one transaction hits the Bitcoin blockchain.

While the payment channel is open, the user is at no risk of not receiving their funds and wanting to withdraw after every $1 is accrued.

### 1.2 Unidirectional Payment channels
The payment channel consists of two on chain transactions. Supload creates the payment channel by sending funds into a Bitcoin multisig address.

Both Supload and the payee party will agree to enter into a off-chain payment channel.

The initial payment channel is funded by Supload into a 2 of 2 multisignature address.

The payee is free to redeem funds whenever they are happy with the payment.

TODO: flesh out this description

![Image of Supload HTLC](https://i.supload.com/Hkl15gj35b.png)




## 2.0 Permanent Decentralized File Storage

Moving the backend storage to the IPFS filesystem allows any uploaded content to Supload to be available in a permanent manner. IPFS is censorship proof file storage that is guaranteed to exist as long as the internet is working.

* **User Benefits -** Video and image hosting sites are notoriously prone to shutting down or having to censor content due to pressure from governments or advertisers. Whether it is from legal pressure for the content they are hosting, or the costs of operation become unbearable.
* **Message Board Benefits -** When a media hosting site goes down, the links to that content are still spread throughout the internet. Broken image links are a longstanding problem for message boards and content aggregation sites such as Reddit. Forcing most moderators to only accept links to a few of the most trusted centralized hosts. But no website can guarantee to operate forever.

### 2.1 Data resolution
Content on IPFS is addressed by a cryptographic hash of the content of the file. IPFS then uses it's own location resolution system built on a Distributed Hash Table. It's much more efficient than the current IPv4 location based system the internet uses. It's quite revolutionary to think of data storage not as, where in the world is the server located that has this data, but rather, who in the world has the file with these contents.

### 2.2 Fetching content if supload.com does not resolve

TODO: description of rewriting links directly to the media in ipfs

#```https://www.supload.com/<ipfshash1>```

### 2.3 Efficiency of data deduplication in IPFS
With IPFS's content hash storage, deduplication of storage is an automatically built in feature. This is an extremely efficient method for mass storage. Duplicate posts of the same data will result in pointing to one copy of the file since the resulting cryptographic hash will be identical.

### 2.4 Blockchains in IPFS
The merkle DAG structure found in blockchains can be easily replicated in IPFS. Past blocks can always be linked by their hash from later ones. The state database that Ethereum uses, can be modeled in IPFS. So storing the current state of Supload can follow the same state model.

Every block in the Supload chain will have a merkleized trie of the current state, a merkle tree of transactions, and a reference to the prior state being modified. Using IPFS to store the state and transaction trees will allow miners to only store small set of data on chain. The deduplication we gain on IPFS can be seen below. Only the state entries that have changed between two blocks will need to be stored.

![State database in IPFS](https://i.supload.com/S1xZdzGXiW.png)


## 3.0 Decentralized State Computation
The most difficult step is moving the current state of Supload out of a centralized database, and into a public blockchain. Most early blockchains were never meant to be more than transactional ledgers. This changed with the launch of Ethereum. Ethereum was the first to introduce a turing complete virtual machine that could be programmed to do any type of computation on the blockchain. But this has its shortcomings.

Presently every Ethereum miner has to independently run each smart contract code in its entirety. That makes smart contracts expensive to run small, quick computations that Supload would require. Also, Ethereum’s variable gas limit restricts the number of computation steps that smart contracts can perform.

### 3.1 Plasma Ethereum framework
Plasma is a framework of smart contracts designed to enable massive scaling and computation on the Ethereum blockchain. We see this as a way to handle the validation of the state of Supload in a blockchain. The root Ethereum contract processes only a very small amount of commitment from child blockchains, drastically reducing fees and allowing a huge number of computations.

Commitments are broadcasted periodically to the root blockchain from the child Plasma chains. Only a tiny amount of commitments are needed for the entire computation of Supload.

TODO: Move this to Sup token section at bottom? Decentralized applications can be reframed as a MapReduce problem with economic incentives for correct activity bonded by the Sup token.

### 3.3 Scalability with blockchains in blockchains

Plasma offers the ability to scale computation by separating data into multiple sub blockchains from the root Plasma chain. This would allow Supload to scale infinitely without running into a problem of block size getting so large miners won't want to participate.

The state on the site can be broken into different categories depending on the content of the upload. Vlogs, memes, documentaries, photography, for example. Sharding the state files allows miners to only focus on their one set of necessary data. They then report their computation to the chain below. The final merkle hash after coalescing all the chains data is the only thing reported to the root Ethereum chain.

This allows a visitor of the site to move to the chain tip of the category they are interested in viewing. They can then go back X number of blocks to view a weeks worth of posts, for example. Get the necessary state files from each block from IPFS.

![Plasma multiple blockchains](https://i.supload.com/Hkg1bhVvjZ.png)



## 4.0 Decentralized Image and Video Compression

The computation needed for image and video Compression is extremely CPU intensive. For the future full length video update to Supload, video files need to be compressed to multiple resolutions (360p, 540p, 720p) to enable a smooth browsing experience depending on users bandwidth. Those different resolution files then need to be split into short one second chunks, to be able to facilitate smooth switching of resolutions depending on deteriorating or improving network conditions.

The golem network[5] offers renting out idle CPU cycles from its network of users. Docker images with binaries for compression and chunking can be uploaded to their Application Registry. Golem network users can reference data stored in IPFS. Run the necessary computation for compression, and upload the finished product back into IPFS.

### 4.1 Docker images in Golem

TODO: description of docker images in Golem




## 5.0 Decentralized Websites

The current site infrastructure is reliant entirely on Amazon Web Services for our backend. Here's an overview.

![Image of current infrastructure](https://i.supload.com/rJgg6LixjZ.png)

Completely decentralizing the backend to Supload will give any developer the ability to create apps and website front ends to our content. They are free to monetize any way they see fit.

This will ensure the long term survival of our blockchain and company. Giving developers access to our backend is giving them access to an already built and thriving social network. No longer having to worry about building a product, then bootstrapping the first users and building a community. They are free to focus on the interface to our content only. This is effectively, crowdsourcing user interfaces.

### 5.1 Crowdsourcing user interfaces

Completely opening up the Supload backend will allow rapid experimentation of interfaces by developers. Websites and apps that would normally be our competitor, now strengthen our product.

Free to rapidly explore new ideas, we will never be able to predict what developers around the world will come up with. Maybe it's new monetization strategies around having users solve hashes in their web browsers to mine cryptocurrencies. Or a new way to interact with a touchscreen interface that no one has thought of. Developers will be able to iterate rapidly.

![Image of decentralized infrastructure](https://i.supload.com/r1xZ28olob.png)

### 5.3 Supload website division

The current Supload website, with our ad revenue sharing business model, will always continue to exist. Nothing has to change about the feature set and user experience that we offer now. The Supload whitepaper is a roadmap to the features we will execute on, and ensure that we are always one of the biggest and most popular portals to the Supload blockchain.

### 5.3 Supload blockchain division

Making the backend decentralized and public creates a new revenue stream for Supload. A certain amount of SUP token will always be required to be included in our blockchain. Whether it's uploading a video, making a comment, upvoting / downvoting a post, will require a small fee. Supload will take a small portion of these fees to continue blockchain development. A majority of the fee will go to miner rewards for running the computation to ensure the correctness and security of our blockchain.


## 6.0 SUP Token Utility

The primary use of our token works in the same way as the Nakamoto consensus to ensure the security of our blockchain.

TODO: Description of chain halting protection in Plasma to penalize bad actors

### 6.1 Token Bonding

If the primary purpose of the SUP token is the reward to miners to compute the current state of the site, then our tokens primary value is derived from this reward. Miners are then financially incentivized to not attack the chain. If the chain halts, the value of the chain declines, effecting the economic price of the SUP token. This creates significant economic incentive for continued correct operation.

This makes the SUP token far more effective in securing the Supload blockchain than any other currency. If we were to bond the chain with Ethereum or Bitcoin, bad actors would have no economic effect on those currencies. The reward would always stay the same.




## 7.0 Acknowledgements
Taylor Gerring - https://blog.ethereum.org/2014/08/18/building-decentralized-web/

Consensys, Introducing IPFS - https://medium.com/@ConsenSys/an-introduction-to-ipfs-9bba4860abd0

IPFS whitepaper - https://ipfs.io/ipfs/QmR7GSQM93Cx5eAg6a6yRzNde1FQv7uL6X1o4k7zrJa3LX/ipfs.draft3.pdf

Plasma whitepaper - http://plasma.io/plasma.pdf

Filecoin whitepaper - https://filecoin.io/filecoin.pdf

Golem Network - http://golemproject.net/doc/DraftGolemProjectWhitepaper.pdf

Ethereum Research Fraud Proofs - https://github.com/ethereum/research/wiki/A-note-on-data-availability-and-erasure-coding

Ethereum Trie JS code - https://github.com/ethereumjs/merkle-patricia-tree

Understanding the Ehereum Trie - https://easythereentropy.wordpress.com/2014/06/04/understanding-the-ethereum-trie/

IPFS block storage discussion - https://www.reddit.com/r/ethereum/comments/44qpks/what_would_be_needed_to_store_the_blockchain_as_a/czs5qnh/
