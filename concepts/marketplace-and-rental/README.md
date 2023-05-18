# Marketplace and Rental

Two core contracts are behind how NiFTyRent works. They are the rental contract and marketplace contract.&#x20;

## Rental Contract

Rental contract stores the essential information about all existing leases, such as leasing NFT's contract and token id, lender account, borrower account, price of the lease, time range of the lease, etc.&#x20;

It also defines functions that enables behaviours of a lease. For example, create a lease, activate a lease, complete a lease, distribute rent based on agreed terms etc.

Everything related to an actual lease are handled by the rental contract. Additionally, this contract also supports LEASE Ownership NFT feature which is a way to verify the ownership of the leasing NFT during the leasing period. More details are on [LEASE Ownership NFT](../../product-doc/lease-ownership-nft/).

## Marketplace Contract

This is the contract that supports the Marketplace feature. It enables users to create, browse and  accept NFT lease listings. For most users, they only interact directly with marketplace contract. Once the needed information is gathered, marketplace contract interacts with rental contract to enable actions to facilitate the actions related to a lease.&#x20;

Allowed NFT contracts will have a Shop in our marketplace to list all leases offers, which will be covered more next on [Shops](shops.md).
