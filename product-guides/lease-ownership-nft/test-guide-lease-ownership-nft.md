# Test Guide - Lease Ownership NFT

In this guide, we will give you some examples to test out the Lease Ownership NFT feature. We will demonstrate using Mintbase and our testnet app ([https://testnet.niftyrent.xyz/app](https://testnet.niftyrent.xyz/app)). You can also use your own NFT to test.

## Context:

Listed here are some terms used through this guide, along with their sample values:

* **Lender** (crypto\_ty.testnet): original lender of the NFT.
* **Borrower** (ty\_dev.testnet): the borrower of the NFT.
* **New Owner / New Lender**(ty\_dev\_3.testnet): new owner to receive the Lease Ownership NFT.
* Royalty split: we will 2 accouts to split the agreed rent price. ty\_dev\_2.testnet (20%), crypto\_ty.testnet (80%). Refer to our [guide on royalty split](../royalty-split-w-mintbase.md) on how it works at NiFTyRent.

The testnet Lease Ownership NFT contract is deployed at **nft-rental.testnet**

## Mint an NFT on Mintbase

Sign in to Mintbase on testnet ([https://testnet.mintbase.xyz/](https://testnet.mintbase.xyz/)) and mint your nft.  For demonstration purpose we added an extra account to split the Royality. You can also skip the Royality setinngs. The rent will then all go to the original lender.  Our sample NFT 's details are listed below:

* contract\_id: tynftstore.mintspace2.testnet
* token\_id：1
* owner: crypto\_ty.testnet

<img src="../../.gitbook/assets/Screenshot 2023-02-26 at 16.41.37.png" alt="" data-size="original">  ![](<../../.gitbook/assets/Screenshot 2023-02-26 at 16.46.02.png>)

###

## Create a new lease on NiFTyRent

Create a new lease with your newly minted NFT. Refer to [how to lend](../how-to-lend.md) for details. We set the rent to be 5 wNEAR,  borrower to be ty\_dev.testnet, duration to be 10 minutes.

![](../../.gitbook/assets/create\_a\_lease.png)

After the lease being created, you can find the new lending in My Lendings. The State will be pending. So it is pending to be accepted. The lease info can also be verified from command line.

![](../../.gitbook/assets/lease\_info.png) ![](../../.gitbook/assets/lease\_detail.png)

###

## Activate the Lease and receive the LEASE Ownership NFT

Next, log in NiFTyRent using the borrower account (e.g. ty\_dev.testnet) and accept the lease from My Borrowings.&#x20;

![](<../../.gitbook/assets/my borrowings.png>)

Now that the lease has been activated, a new LEASE Ownership NFT should show up in the lender's (crypto\_ty.testnet) NEAR wallet like below. This authorises the ownership of the underlying NFT.

![](<../../.gitbook/assets/Ownership\_NFT\_for\_lender (1).png>)

###

## Transfer the LEASE Ownership NFT to a new owner

The LEASE Ownership NFT, like other NFTs, can be transferred to other accounts. Owner of the LEASE owership NFT will become the new lender of the underlying lease. Here, we transferred the ownership nft to a new owner, ty\_dev\_3.testnet. We can verify that in the new owner's wallet. The updated lease information can be verified through command line - note the lender\_id is now ty\_dev\_3. If you logged in NiFTyRent using the new lender's account, the lease would also be shown in My Lendings page.

![](../../.gitbook/assets/ownership\_nft\_for\_new\_lender.png)![](../../.gitbook/assets/lease\_detail\_new\_lender.png)

![](<../../.gitbook/assets/my\_lendings\_new\_lender (2).png>)



## Claim back the rented NFT & Verify result

With the LEASE Ownership NFT, the new lender will be able to claim back the lease once it expired. Let's go ahead doing that. This will result in the following outcomes:

* The under leased NFT is sent to the LEASE Ownership NFT owner (ty\_dev\_3.testnet). Check the NFT info below. Note the owner field change.
* Since royalty split was configured in our earlier-minted NFT, the agreed rent will be shared between the original lender (80%) and the perpetual royalty split account (20%). In our case, the rent is 0.5 wNEAR. So, original lender (crypto\_ty.testnet) received 0.4 wNEAR and the royale (ty\_dev\_2.testnet) received 0.1 wNEAR.

![](../../.gitbook/assets/nft\_info\_after\_claim\_owned\_by\_new\_lender.png)

