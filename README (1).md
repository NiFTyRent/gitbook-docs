---
description: How does renting work on NiFTyRent
---

# Renting Flow

Utility NFTs can be lent and borrowed between two individuals. Some examples of a utility NFT can be passes to exclusive content, web3 in-game assets, event tickets and so on. The owner of an NFT can create a lease contract indicating the intention to rent the NFT. A borrower can then check the lease contract condition and decides whether or not to accept the lease.&#x20;

NiFTyRent implements a Lease contract which allows NFT lenders to configure the lease conditions and share it with a borrower. Sample lease conditions include rent price, lease expiration date, payout lists.  Borrowers can accept the lease after checking the conditions by attaching the agreed rent to the transaction.  Once the lease contract got accepted by the borrower, the NFT will be transferred from the owner account to the the service account and the borrower can start using NFT's features through RPC calls to the lease contract. Rent will be temporarily kept at the service account during the lease period. Once the lease ends, the lender can safely claim back his/her NFT along with the agreed rent.

Any NFT that implements [NEP-171](https://github.com/near/NEPs/blob/master/specs/Standards/Tokens/NonFungibleToken/Core.md) and [NEP-178](https://github.com/near/NEPs/blob/master/specs/Standards/Tokens/NonFungibleToken/ApprovalManagement.md) can utilise NiFTyRent to achieve the renting feature.

With the Markteplace feature being introduced, NiFTyRent now allows project (such as games, DAOs, Mintbase stores) to enable rental feature on their NFTs. Projects that want their users to rent NFT tokens, can now add their NFT contracts onto NiFTyRent platform. Owners of the projects tokens can then list lease offers and borrowers can choose the most interesting NFT lease to rent. More on this in [Marketplace and Rental](concepts/marketplace-and-rental/).
