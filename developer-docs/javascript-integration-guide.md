# JavaScript Integration Guide

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>How the rented NFT works under the hood</p></figcaption></figure>

The above digraph outlined the main logic behind the scenes of interacting with a rented NFT via NiftyRent.

But you don't have to know all the bolts and nuts to have your project support NFT rental. The important things are:

1. First, prepare your NFTs. Find out the contract address and the token ids of them. (If you haven't made your NFTs, you can try [Mintbase.io](htttps://mintbase.io))
2. Then, import [@niftyrent/sdk](https://www.npmjs.com/package/@niftyrent/sdk) into your JavaScript project, and use it in the places where you want to know if a given user has the right to use an NFT at the time requested.
3. Last but not the least, provide instructions to your users about how to rent NFTs. (We are working on implementing shopfront pages for every project now. When it's ready, it will be much simpler for your user to do it, and you can even embed the page into your app or game.)

### Use the JavaScript SDK

First, add the SDK as a dependency of your project:

```
npm add @niftyrent/sdk
```

Then you can add the logic for check the current user of any NFT.

The following is an example to support a "Magic Sword" NFT item in a game.

```javascript
import { NiftyRent } from "@niftyrent/sdk"

// A list of the corresponding NFT token ids.
// For the in-app object (or in-game item) you may want multiple copy of it.
// Therefore you will multiple corresponding NFTs, each one with a unique token id.
const MAGIC_SWORD_TOKEN_IDS = ["magic_1", "magic_2", ...];

Class YourApp {
    async appInit() {
        // Config and initialize NiftyRent SDK.
        this.niftyrent = await new NiftyRent({
            defaultContractAddr: <YOUR_NFT_CONTRACT_ADDRESS>,
            allowedRentalProxies: ["nft-rental.testnet"],
        }).init();
    }
    
    async playerInventory(nearAccountId) {
        let items = []
        const results = await Promise.all(MAGIC_SWORD_TOKEN_IDS.map(tokenId =>
                this.niftyrent.is_current_user(nearAccountId, tokenID)
            ));
        const nMagicSword = results.filter(x => x).length;
        if (nMagicSword > 0) {
            items.push({name: "Magic sword", count: nMagicSword})
        }
        
        // Check other items ...
        
        return items;
    }
}
```

{% hint style="info" %}
Some method of `NiftyRent` returns `Promise`s, because it need to make API calls behind the scenes. Using JavaScript's `async/await` syntax could make your life easier :sunglasses:
{% endhint %}

In this code example, `is_current_user` method is used to check whether a given NEAR account is the current user of the "Magic Sword" NFTs.

An account will recognised as the current user of an NFT, if:

* it's the owner when the NFT is not under a lease, or
* it's the borrower when the NFT is under a lease.

