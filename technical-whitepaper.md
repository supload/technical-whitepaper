# Supload Technical Whitepaper

[1]
Evaluating this context in a larger diagram of any systems infrastructure, it’s obvious that our current web isn’t as privacy secure or censorship resistant as we desire. Economies of scale have allowed single institutions to offer a vast amount of processing power and storage on the internet for very low prices, thereby increasing their market share to a point where they individually control large segments of internet activity, often under the supervision of less-than-savvy governments. In a post-borders era where the Internet knows no bounds, such jurisdiction has little or no meaning.

An outline of the future decentralized features of supload image and video hosting. The ultimate end goal is a permanent / uncensorable copy of the hosted content in the ipfs cloud. The backend state of the site, and computation is publically available on a Ethereum secondary layer blockchain utilizing the forthcoming Plasma framework.

This documents will be separated into the main three future technical / decentralized feature upgrades.

1. **Payment Scalability -** Integration with the lightning network on the Bitcoin and Litecoin blockchains. This will facilitate near realtime micropayments to the Supload user as their content is generating pageviews. Keeping the bitcoin blockchain free of many small payments.
2. **Permanent Decentralized Storage -** All uploads to Supload will be permanently stored in the uncensorable filecoin network.
3. **Decentralized Website State -** Utilizing the proposed Plasma secondary layer to the Ethereum blockchain. Computation and storage of current website state (votes, user authorization, moderation) will be able to be computed in a decentralized peer to peer network.

## 1.0 Payment Scalability

With a low threshold of allowing users to withdraw their bitcoin earnings after earning only $1.00 USD, we need to think to the future about how to scale these payments. With any type of growth, Supload could potentially spam the bitcoin blockchain with many low $1.00 transactions.

Users are currently incentivized to withdraw their earnings as soon as they reach the $1.00 minimum withdraw threshold. Anything else is entrusting a 3rd party(Supload) to hold their earnings until they withdraw, is poor bitcoin security from the user standpoint. Entrusting a third party to hold you coins is a bad crypto practice.

The solution is to move these payments off the primary bitcoin blockchain, onto a secondary layer.

### 1.1 :zap: Lightning Network

The Lightning Network allows us to stream payments to our users. Instead of allowing users to get paid after they've earned $1.00. Lightning makes it so Supload can pay users every ten minutes when our analytics have finished running.

The Lightning Network makes it so we can transact very small amounts of bitcoin in near realtime, for almost no fee. This will be a feature that is available to the highest ranked users on Supload. A few of our biggest content creators are responsible for a majority of the payments.

The lightning network will provide an extra layer of trust for users. As the payments are being updated, the payee is receiving a new signed Hashed Timelock Contracts from Supload. With the committed amount of payment. At that point, it's impossible for the payer (Supload) to go back on the agreed upon payment amount. The funds are then being held in a contract on the bitcoin blockchain.

The amount owed to the content creator will update every 10 minutes when we run our analytics, adjusting for pageviews in that period of time.

When the user wants to finalize and receive their funds, they can close the payment channel with Supload. The users wallet will the take the most current Timelock Contact and publish it to the bitcoin blockchain. Only one transaction hits the bitcoin blockchain.

While the payment channel is open, the user is at no risk of not receiving their fund and wanting to withdraw after every $1 is accrued.

![Image of Supload HTLC](https://i.supload.com/rJlg-nyqcW.png)

Analytics run every 10 minutes. Updating the amount owed to the Supload user in the contract.

![Image of Supload HTLC](https://i.supload.com/rJlg-nyqcW.png)

### Unidirectional Payment channels
The payment channel consists of two on chain transactions. Supload creates the payment channel by sending funds into a bitcoin multisig address.

Both Supload and the payee party will agree to enter into a off-chain payment channel.

The initial payment channel is funded by Supload into a 2 of 2 multisignature address.

The payee is free to redeem funds whenever they are happy with the payment.




## 2.0 Decentralization
The end goal of supload is to completely decentralize the storage and computation of the current state of the site. This will create a public, uncensorable network. Anyone can access the images and video, being publicly available on the filecoin cloud. The current state of the site (comments, votes, titles, descriptions) will be held in a publicly accessible blockchain based on the forthcoming Plasma secondary blockchain on the ethereum network.

The goal is to decentralize the backend, allowing anyone to be able to build frontends to our content. Opening the backend will give developers the ability to create apps and website frontends to our content. They are free to monetize any way they see fit.

This will ensure the long term survival of our blockchain and product. Giving developers access to our backend is giving them access to an already built and thriving community. No longer having to worry about building a product, then getting a user base and building a community. They are free to focus on the interface to our content only. This is in effect, crowdsourcing the user interface.

### 2.1 Crowdsourcing User Interfaces
While a single company like Supload may never be able to build the best possible frontend to our content. Opening up the backend will allow rapid experimentation of interfaces by developers. Websites and apps that would normally be our competitor, now strengthen our core product. We will never be able to predict what this perfect interface could look like.

### 2.2 User Interface Incentive





## 3.0 Permanent Decentralized File Storage
Content on IPFS is addressed by the Base58 encoded hash of the content of the file.

IPFS allows us to replace a standard CDN with a distributed hash table pointing to file blobs.

Moving the backend storage to the IPFS filesystem allows any uploaded content to Supload to be insured to be available for the rest of time. A censorship proof file storage that is guaranteed to exist long after Supload ceases to exist. This is desirable for users and content aggregation sites such as reddit.

* **User Benefits -** Video and Image hosting sites are notoriously prone to shutting down. Whether it is legal pressure for the content they are hosting, or the costs of operation become unbearable.
* **Content Aggregation Site Benefits -** When a content hosting site goes down, the links for that content are still spread throughout the internet. Broken image links is a notorious problem for sites like Reddit. Forcing most Reddit moderators to only accept links to one to two well trusted centralized hosts.

### 3.1 Data Resolution
Filecoin uses it's own location resolution system built on a Distributed Hash Table. It's much more efficient than the current IPv4 location based system the internet uses.

### 3.2 Fetching content if Supload.com does not resolve
#```https://www.supload.com/<ipfshash1>```

### 3.3 Efficiancy of data deduplication in IPFS
IPFS addresses content based on the hash of the objects contents, not by it's location. Duplication of the same images and videos will result in only one copy being stored.





## 4.0 Decentralized state database
The final step in complete decentralization of Supload, is removing the need to have servers at all.

The current state of Supload needs to be removed out of a centralized database, and into a public blockchain.

### 4.1 Storage of state database
The totality of IPFS objects forms a cryptographically authenticated data structure known as a Merkle DAG (Directed Acyclic Graph).

This is one of the most exciting use cases for IPFS. A blockchain has a natural DAG structure in that past blocks are always linked by their hash from later ones.

All that needs to be stored then in the Supload blockchain is a hash pointing to the current state of Supload in IPFS.




### 4.2 Plasma Ethereum Framework
Plasma is a framework of contracts, to enable massive scaling and computation on the Ethereum blockchain. We see this as a way to handle the validation of the state of the site in a blockchain.

Plasma is a proposed smart contract to the Ethereum network by Joseph Poon and Vitalik Buterin. Plasma is a series of contracts which runs on top of main Ethereum blockchain. The root network contract process only very small amount of commitment from child Blockchain which can do a huge number of computations.

The special things is that all commitment are broadcasted periodically on the root Blockchain time to time from the child.

Commitments are broadcasted periodically to the root blockchain from the child Plasma chains. Only a tiny amount of commitments is needed for the entire computation of Supload.

### 4.3 Blockchains in Blockchains




## 5.0 Token Utility
The safety mechanism in Pulse blockchains is chain halting if bad actors are found on the network. The easiest way to handle a bad miner, is not to try to convince the miner to act nicely, but for everyone to drop out of the chain all together. If miners are earning fees for processing Suploads data, from the cost of inclusion of uploads into the chain.

### 5.1 Token Bonding
At this point, the primary purpose of the SUP token is the reward to miners to compute the state of the site. If our tokens primary value is this, chain halting is discouraged. If the chain halts, the value of the chain declines, creating significant economic incentive for continued operation.



## 6.0 Acknowledgements
Taylor Gerring - https://blog.ethereum.org/2014/08/18/building-decentralized-web/

IPFS block storage discussion - https://www.reddit.com/r/ethereum/comments/44qpks/what_would_be_needed_to_store_the_blockchain_as_a/czs5qnh/

Consensys, Introducing IPFS - https://medium.com/@ConsenSys/an-introduction-to-ipfs-9bba4860abd0

IPFS whitepaper - https://ipfs.io/ipfs/QmR7GSQM93Cx5eAg6a6yRzNde1FQv7uL6X1o4k7zrJa3LX/ipfs.draft3.pdf
