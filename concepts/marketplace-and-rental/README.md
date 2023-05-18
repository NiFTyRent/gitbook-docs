---
description: The smart contracts behind NiFTyRent
---

# Marketplace and Rental

Two core contracts are used in NiFTyRent. They are the rental contract and marketplace contract.&#x20;

One the high level, Marketplace contract manages lease offers creating and removing, while Rental contract handles behaviours of successfully accepted leases. The two contracts will interacts with each other.

## Rental Contract

Rental contract stores the essential information about all accepted leases, such as leasing NFT's contract and token id, lender account, borrower account, price of the lease, time range of the lease, etc. It also defines behaviours of an accepted lease. For example, activate a lease, complete a lease, distribute rent based on agreed terms, etc.

Additionally, this contract also supports LEASE Ownership NFT feature which is a way to verify the ownership of the leasing NFT during the lease's life time. More details are on [LEASE Ownership NFT](../../product-doc/lease-ownership-nft/).

## Marketplace Contract

This contract supports the Marketplace feature. It enables users to create, browse and accept NFT lease offers. For most users, their NFT renting journey starts with the marketplace contract. Once the needed information is gathered to create a lease, marketplace contract interacts with the rental contract set the lease up.

One important thing to not is that, for NFT tokens to be rented using our Marketplace, their NFT contracts must be registered on NiFTyRent. What this means for a project (e.g. a game, a DAO) is that, to make their tokens rentable among users, the project must register the corresponding NFT contract on NiFTyRent. Once the contract got registered, the corresponding tokens can be rented among users freely.

When an NFT contracts got registered on NiFTyRent, a Shop frontpage will be created for them in our Marketplace. All lease offers for the corresponding NFT tokens will be listed in the matching Shop. More details will be covered in [Shops](shops.md).
