# Lease Ownership NFT

Leasing your NFT won't change your ownership over the NFT. This means that while your NFT is on lease, as the true owner you should still be able to prove your ownership, transfer your NFT ownership, or even trade it. Meanwhile, those who your transferred your NFT ownership to should be able to receive the NFT once after the lease completes.&#x20;

NiFTyRent enables users to do all those things, by providing owners Lease Ownership NFTs.&#x20;

At the time of a lease's activation, the lender will be issued a Lease Ownership NFT token. This Ownership NFT authorises the lender's ownership of the under-leased NFT. The lender can then transfer the ownership NFT at his or her will, or even trade this ownership NFT token on supported marketplaces.&#x20;

When he/she does so, the receiver of the ownership NFT will become the new lender of the underlying lease. Once the lease expired, the owner of the ownership NFT will be able to claim back the rented NFT. The agreed rent will still go to the original lender (and any payout accounts if it applies).

## Implementation

Lease Ownership NFT supports the following NEAR NFT standards:

* [NEP-171: Core](https://nomicon.io/Standards/Tokens/NonFungibleToken/Core)
* [NEP-177: Metadata](https://nomicon.io/Standards/Tokens/NonFungibleToken/Metadata)
* [NEP-181: Enumeration](https://nomicon.io/Standards/Tokens/NonFungibleToken/Enumeration)
* [Events](https://nomicon.io/Standards/Tokens/NonFungibleToken/Event)

A sample ownership NFT token looks like the following in wallet. Some core information includes:

* Token title: specifies the NiFTyRent Lease Ownership.
* Description: includes NiFTyRent's lease\_id and the information about the underlying renting NFT.

![](../../.gitbook/assets/Ownership\_NFT\_for\_lender.png)

For more details on how to use a Lease Ownership NFT, please refer to our [user example](how-to-use-lease-ownership-nft-an-example.md).
