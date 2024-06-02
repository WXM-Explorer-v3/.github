
# WXM Explorer V3

WXM Explorer V3 is an extension for [WXM Explorer](https://weatherxm.com/explorer) with some additional features such as bounty creation, bounty map and bounty claiming.

## Changes
1. **Frontend** - 
    * Added a page for bounties
    * Added WalletConnect
    * Added BountyCells to MapBox
    * Added Bounty HeatMap to MapBox
    * Added feature to create/contribute to a bounty.

2. **Smart Contracts** -
    * Added [BountyManager.sol](https://github.com/WXM-Explorer-v3/contracts/blob/develop/src/0.8.20/BountyManager.sol)
    * Integrated Chainlink Functions for seamless and secured bounty claiming.

## Bounty Flow
1. **Bounty Creation** - Anyone can connect their wallet in the website and Go to "Bounty View" and click in the region in which they want to create the bounty.

2. **Bounty Contribution** - Users can also contribute WXM tokens to the existing bounties.

3. **Claiming Bounty** -
    * Get Bearer token from [WXM API](api.weatherxm.com/api/v1/docs/#/)
    * Download this [script](https://github.com/WXM-Explorer-v3/contracts/blob/develop/chainlink-functions/user_request.js)
    * Run the script - 

    ```node user_request.js "YOUR_BEARER_TOKEN" "YOUR_DEVICE_ID" "YOUR_REGISTERED_WALLET" "YOUR_PRIVATE_KEY" "BOUNTY_ID"```

4. **Claim Validation** -
    * Chainlink Functions make an API call to get the user's device info.
    * It also checks if the device is set up in the eligible bounty region by creating a virtual polygon around the bounty's center.
    * At the end, it checks if the claim request is made by the registered wallet address.

## Adapting to the current WXM Implementation
1. The frontend changes have been made keeping the WXM team’s approach in consideration.

2. This makes it easy to be taken to production just by adding  some minor UI fixes

3. The Chainlink script execution can be added to the API Backend to make the flow more seamless

4. An extra layer of bearer token encryption while claiming bounty would make this flow un-breachable


## Deployments (Arbitrium Sepolia)
**BountyManager** - 0x89fb12264B5D9DA8604cd9BcB6Abb593a91B172e

**MockWXM Token** - 0x4Fc5C4461Ca5Fdc7b9D91c6B0DEfEB5D9Fb5Eb43

**Chainlink Functions SubscriptionID** - 86