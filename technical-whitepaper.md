# Supload Technical Whitepaper

[1]
Evaluating this context in a larger diagram of any systems infrastructure, it’s obvious that our current web isn’t as privacy secure or censorship resistant as we desire. Economies of scale have allowed single institutions to offer a vast amount of processing power and storage on the internet for very low prices, thereby increasing their market share to a point where they individually control large segments of internet activity, often under the supervision of less-than-savvy governments. In a post-borders era where the Internet knows no bounds, such jurisdiction has little or no meaning.

The current internet is nowhere near as privacy secure or censorship resistant as we desire. While the first wave of internet web applications have sped up the adoption of the internet by the world. The internet has created the largest corporations in history, that control our private data, to use and share for their own benefit.

The forthcoming decentralized internet is an attempt to move our personal data and privacy out of corporate data silos.

This whitepaper is an outline of the future decentralized features of supload image and video hosting. The end goal is a permanent / uncensorable copy of the hosted content. All data, website state and the tools to interact with this data will be freely available to public.

This documents will be separated into the main three future technical / decentralized feature upgrades.

1. **Payment Scalability -** Integration with the lightning network on the Bitcoin and Litecoin blockchains. This will facilitate near realtime micropayments to Supload users as their content is generating pageviews. Think of it as streaming payments.
2. **Permanent Decentralized Storage -** All uploads to Supload will be permanently stored in the uncensorable filecoin network.
3. **Decentralized Website State -** Utilizing the proposed Plasma smart contract framework on the Ethereum blockchain, computation of the current website state (votes, user authorization, moderation) will be finalized on our own public blockchain. Consensus will be reached, and miners will be rewarded with the SUP token.
4. **Decentralized Video Compression -** To provide the best possible user experience for full length video, computation needs to be done to separate large video files into small chunks to facilitate fast loading when scrubbing through a videos timeline. The golem network is a possible solution to renting cpu time from a network of users to aid in compressing video.


## 1.0 Payment Scalability

With a low threshold of allowing users to withdraw their bitcoin earnings after earning only $1.00 USD, we need to think to the future about how to scale these payments. With any type of growth, Supload could potentially spam the bitcoin blockchain with many low $1.00 transactions.

Users are currently incentivized to withdraw their earnings as soon as they reach the $1.00 minimum withdraw threshold. Anything else is entrusting a 3rd party(Supload) to hold their earnings until they withdraw, is poor bitcoin security from the user standpoint. Entrusting a third party to hold you coins is a bad crypto practice.

The solution is to move these payments off the primary bitcoin blockchain, onto a secondary layer.

### 1.1 :zap: Lightning Network

The Lightning Network allows us to stream payments to our users. Instead of allowing users to withdraw their earning after they've earned $1.00. Lightning makes it so Supload can pay users every ten minutes when our analytics have finished running.

The Lightning Network makes it so we can transact very small amounts of bitcoin in near realtime, for almost no fee. This will be a feature that is available to the highest ranked users on Supload. A few of our biggest content creators are responsible for a majority of the payments.

The lightning network will provide an extra layer of trust for users. As the payments are being updated, the payee is receiving a new signed Hashed Timelock Contracts from Supload. With the committed amount of payment. At that point, it's impossible for the payer (Supload) to go back on the agreed upon payment amount. The funds are then being held in a contract on the bitcoin blockchain.

The amount owed to the content creator will update every 10 minutes when we run our analytics, adjusting for pageviews in that period of time.

When the user wants to finalize and receive their funds, they can close the payment channel with Supload. The users wallet will the take the most current Timelock Contact and publish it to the bitcoin blockchain. Only one transaction hits the bitcoin blockchain.

While the payment channel is open, the user is at no risk of not receiving their fund and wanting to withdraw after every $1 is accrued.

Analytics run every 10 minutes. Updating the amount owed to the Supload user in the contract.


### 1.2 Unidirectional Payment channels
The payment channel consists of two on chain transactions. Supload creates the payment channel by sending funds into a bitcoin multisig address.

Both Supload and the payee party will agree to enter into a off-chain payment channel.

The initial payment channel is funded by Supload into a 2 of 2 multisignature address.

The payee is free to redeem funds whenever they are happy with the payment.

![Image of Supload HTLC](https://i.supload.com/Hkl15gj35b.png)



## 2.0 Permanent Decentralized File Storage

Moving the backend storage to the IPFS filesystem allows any uploaded content to Supload to be insured to be available for the rest of time. IPFS is censorship proof file storage that is guaranteed to exist as long as the internet is working.

* **User Benefits -** Video and Image hosting sites are notoriously prone to shutting down or having to censor content due to pressure from governments or corporations. Whether it is legal pressure for the content they are hosting, or the costs of operation become unbearable.
* **Content Aggregation Site Benefits -** When a content hosting site goes down, the links to that content are still spread throughout the internet. Broken image links is a longstanding problem for message boards and content aggregation such as Reddit. Forcing most moderators to only accept links to one to two of the most trusted centralized hosts.

### 2.1 Data Resolution
Content on IPFS is addressed by the Base58 encoded hash of the content of the file.

Filecoin uses it's own location resolution system built on a Distributed Hash Table. It's much more efficient than the current IPv4 location based system the internet uses.

### 2.2 Fetching content if Supload.com does not resolve
#```https://www.supload.com/<ipfshash1>```

### 2.3 Efficiancy of data deduplication in IPFS
IPFS addresses content based on the hash of the objects contents, not by it's location. Duplication of the same images and videos will result in only one copy being stored. This is an extremely efficient method for video and image storage. Duplicate posts of the same data will result in pointing to one copy of the file since the resulting base58 hash will be identical.







## 3.0 Decentralized state database
The final step in complete decentralization of Supload, is removing the need to have servers at all.

The current state of Supload needs to be removed out of a centralized database, and into a public blockchain.

### 3.1 IPFS Storage of state database
IPFS is ideal to use as a database to store the current state of the site. The ability to de-duplicate data works in Suploads favor, since most state updates only change on the newest most popular uploads.

The totality of IPFS objects forms a cryptographically authenticated data structure known as a Merkle DAG (Directed Acyclic Graph).

This is one of the most exciting use cases for IPFS. A blockchain has a natural DAG structure in that past blocks are always linked by their hash from later ones.

All that needs to be stored then in the Supload blockchain is a hash pointing to the current state of Supload in IPFS.

### 3.2 Plasma Ethereum Framework
Plasma is a framework of contracts, to enable massive scaling and computation on the Ethereum blockchain. We see this as a way to handle the validation of the state of the site in a blockchain.

Plasma is a proposed smart contract to the Ethereum network by Joseph Poon and Vitalik Buterin. Plasma is a series of contracts which runs on top of main Ethereum blockchain. The root network contract process only very small amount of commitment from child Blockchain which can do a huge number of computations.

The special things is that all commitment are broadcasted periodically on the root Blockchain time to time from the child.

Commitments are broadcasted periodically to the root blockchain from the child Plasma chains. Only a tiny amount of commitments is needed for the entire computation of Supload.

### 3.3 Blockchains in Blockchains


## 4.0 Decentralization
The end goal of supload is to completely decentralize the storage and computation of the current state of the site. This will create a public, uncensorable network. Anyone can access the images and video, being publicly available on the filecoin cloud. The current state of the site (comments, votes, titles, descriptions) will be held in a publicly accessible blockchain based on the forthcoming Plasma secondary blockchain on the ethereum network.

The goal is to decentralize the backend, allowing anyone to be able to build frontends to our content. Opening the backend will give developers the ability to create apps and website frontends to our content. They are free to monetize any way they see fit.

This will ensure the long term survival of our blockchain and product. Giving developers access to our backend is giving them access to an already built and thriving community. No longer having to worry about building a product, then getting a user base and building a community. They are free to focus on the interface to our content only. This is in effect, crowdsourcing the user interface.

### 4.1 Crowdsourcing User Interfaces
While a single company like Supload may never be able to build the best possible frontend to our content. Opening up the backend will allow rapid experimentation of interfaces by developers. Websites and apps that would normally be our competitor, now strengthen our core product. We will never be able to predict what this perfect interface could look like.

### 4.2 User Interface Incentive



## 5.0 Token Utility
The safety mechanism in Pulse blockchains is chain halting if bad actors are found on the network. The easiest way to handle a bad miner, is not to try to convince the miner to act nicely, but for everyone to drop out of the chain all together.

### 5.1 Token Bonding
The primary purpose of the SUP token is the reward to miners to compute the current state of the site. If our tokens primary value is derived from this reward, miners are financially incentive to not attack the chain. If the chain halts, the value of the chain declines, effecting the economic price of the SUP token. Creating significant economic incentive for continued operation.

This makes the SUP token far more effective in protecting the Supload chain than any other currency. Bonding the chain with Ethereum of Bitcoin, bad actors will have no effect on the economic price of either of those coins.


## 6.0 Acknowledgements
Taylor Gerring - https://blog.ethereum.org/2014/08/18/building-decentralized-web/

IPFS block storage discussion - https://www.reddit.com/r/ethereum/comments/44qpks/what_would_be_needed_to_store_the_blockchain_as_a/czs5qnh/

Consensys, Introducing IPFS - https://medium.com/@ConsenSys/an-introduction-to-ipfs-9bba4860abd0

IPFS whitepaper - https://ipfs.io/ipfs/QmR7GSQM93Cx5eAg6a6yRzNde1FQv7uL6X1o4k7zrJa3LX/ipfs.draft3.pdf
