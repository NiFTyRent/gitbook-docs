# How to use Lease Ownership NFT - An example

In this guide, we will walk you through an example of using Lease Ownership NFT features. By the end of this guide, you should have a good idea about how Ownership NFT works for your lease. We will demonstrate by using Mintbase and our testnet dApp ([https://testnet.niftyrent.xyz/app](https://testnet.niftyrent.xyz/app)). You can also use your own NFT on NEAR to test.

## Context:

Listed here are some terms used throughout this guide, along with their sample values:

* **Lender** (crypto\_ty.testnet): original lender of the NFT.
* **Borrower** (ty\_dev.testnet): the borrower of the NFT.
* **New Owner / New Lender**(ty\_dev\_3.testnet): new owner to receive the Lease Ownership NFT.
* Royalty split: we will configure 2 accounts to share the agreed rent. ty\_dev\_2.testnet (20%), crypto\_ty.testnet (80%). Refer to our [guide on royalty split](../royalty-split-w-mintbase.md) on how royalty works at NiFTyRent.

For developers that want to query the contract using command line,  we have deployed the contract on testnet at **nft-rental.testnet.** You don't need a command line to use the Ownership NFT token. All the steps here can be done through the UI at NiFTyRent and Mintbase.

## Mint an NFT on Mintbase

Sign in to Mintbase on testnet ([https://testnet.mintbase.xyz/](https://testnet.mintbase.xyz/)) and mint your NFT.  For demonstration purpose, we added an extra account to split the Royalty. You can also skip the Royalty settings. The rent will then all go to the original lender at the end.  The sample NFT 's details are listed below:

* contract\_id: tynftstore.mintspace2.testnet
* token\_id：1
* owner: crypto\_ty.testnet

<img src="../../.gitbook/assets/Screenshot 2023-02-26 at 16.41.37.png" alt="" data-size="original">  ![](<../../.gitbook/assets/Screenshot 2023-02-26 at 16.46.02.png>)

###

## Create a New Lease on NiFTyRent

Create a new lease with your newly minted NFT. Refer to [how to lend](../lend-your-nft.md) for details. We set the rent to be 0.5 wNEAR,  borrower to be ty\_dev.testnet, duration to be 10 minutes.

![](../../.gitbook/assets/create\_a\_lease.png)

After the lease being created, you can find the new lending in My Lendings. The State will be pending. So it is pending to be accepted. The lease info can also be verified from command line.

![](../../.gitbook/assets/lease\_info.png) ![](../../.gitbook/assets/lease\_detail.png)

###

## Activate the Lease and Receive LEASE Ownership NFT Token

Next, log in NiFTyRent using the borrower account (e.g. ty\_dev.testnet) and accept the lease from My Borrowings.&#x20;

![](<../../.gitbook/assets/my borrowings.png>)

Now that the lease has been activated, a new LEASE Ownership NFT should show up in the lender's (crypto\_ty.testnet) NEAR wallet like below. This token authorises the ownership of the underlying NFT.

![](<../../.gitbook/assets/Ownership\_NFT\_for\_lender (1).png>)

###

## Transfer the LEASE Ownership NFT to a New Owner

The LEASE Ownership NFT, like other NFTs on Near, can be transferred to other accounts. Owner of the LEASE owership NFT will become the new lender of the underlying lease. In this example, we transferred the Ownership NFT to a new owner, ty\_dev\_3.testnet. The Ownership NFT token will then be shown in the new owner's wallet. The updated lease information can also be verified through command line - note the lender\_id is now ty\_dev\_3. If you logged in NiFTyRent using the new lender's account, the lease also be shown in My Lendings page.

![](../../.gitbook/assets/ownership\_nft\_for\_new\_lender.png)![](../../.gitbook/assets/lease\_detail\_new\_lender.png)

![](<../../.gitbook/assets/my\_lendings\_new\_lender (2).png>)



## Claim Back the Rented NFT & Verify Result

With the LEASE Ownership NFT token, the new lender will be able to claim back the lease once it expired. Let's go ahead doing that. This will result in the following outcomes:

* The under leased NFT is sent to the LEASE Ownership NFT owner (ty\_dev\_3.testnet). Check the NFT info below. Note the owner field change.
* Since royalty split was configured in our earlier-minted NFT, the agreed rent will be shared between the original lender (80%) and the perpetual royalty split account (20%). In our case, the rent is 0.5 wNEAR. So, original lender (crypto\_ty.testnet) received 0.4 wNEAR and the royale (ty\_dev\_2.testnet) received 0.1 wNEAR.

![](../../.gitbook/assets/nft\_info\_after\_claim\_owned\_by\_new\_lender.png)



Thanks for following the example to this point. Now, you have already got a good understanding on the Lease Onwership NFT and how it works. Go ahead and try your own lease on our dApp.

