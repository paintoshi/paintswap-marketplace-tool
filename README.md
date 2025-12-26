# Sonic Marketplace - Cancel Listings & Offers Tool

A standalone HTML tool for managing and canceling NFT listings and offers on the Sonic network marketplace.

## Features

- **Wallet Connection**: Connect to MetaMask or other Web3 wallets, automatically switches to Sonic network (Chain ID: 146)
- **Fetch Listings**: Retrieves all listings from the marketplace using Etherscan API v2 with pagination support
  - Supports both single listings (`NewListing` events) and bulk listings (`NewListingBatch` events)
- **Fetch Offers**: Retrieves all offers from the marketplace using Etherscan API v2 with pagination support
  - Supports both individual offers (`NewOffer` events) and collection offers (`NewCollectionOffer` events)
- **Event Filtering**: Filters `NewListing`, `NewListingBatch`, `NewOffer`, and `NewCollectionOffer` events to extract marketplace IDs and offer IDs
- **Single Cancellation**: Cancel individual listings or offers by clicking their ID buttons
- **Batch Cancellation**: Select multiple listings or offers with checkboxes and cancel them all at once

## Usage

1. Open `index.html` in a web browser
2. Click "Connect Wallet" and approve the connection in your wallet
3. Enter your Etherscan API key
4. **For Listings**:
   - Click on the "Listings" tab (default)
   - Click "Fetch All Listings" to retrieve all listings (includes both single and bulk listings)
   - Cancel listings individually or select multiple and use "Cancel Selected Listings"
   - Use the "Explore Batch Listings" link to view bulk listings on Sonicscan
5. **For Offers**:
   - Click on the "Offers" tab
   - Click "Fetch All Offers" to retrieve all offers (includes both individual and collection offers)
   - Cancel offers individually or select multiple and use "Cancel Selected Offers"
   - Use the "Explore Collection Offers" link to view collection offers on Sonicscan

## Configuration

- **Marketplace Contract**: `0x0c558365eeff4b057fdbed91bc3650e1a00018b4`
- **Network**: Sonic (Chain ID: 146)
- **Event Signatures**:
  - `0x217bd5b40e04ee284d8ebf246fe31b6cf1b5aa0fc343ce0ef5325ee90ef40bea` (NewListing event)
  - `0x0cdb8311c2de3f81939aa0eecb022aff27d218b8528dcacc2a6c89f11002ff54` (NewListingBatch event)
  - `0x51ddc3ce4e6137c19b8b4521871ae05623a9c72df697faf2fdfd1b1a639170b3` (NewOffer event)
  - `0x2f733bc538846de02f3e4be211841f934a46b78240dc1377445df86b187f7e27` (NewCollectionOffer event)

## Requirements

- Modern web browser with Web3 wallet extension (MetaMask recommended)
- Etherscan API key (get one at https://etherscan.io/apis)
- Internet connection

## Notes

- The tool uses Etherscan API v2 format with `chainid=146` for Sonic network
- Listings and offers are sorted by ID (latest first)
- The tool filters for `NewListing`, `NewListingBatch`, `NewOffer`, and `NewCollectionOffer` events
- **Bulk Listings**: When multiple NFTs are listed in a single transaction, all marketplace IDs from the batch are extracted and displayed individually
- **Collection Offers**: Offers made on entire collections (not specific token IDs) are supported and can be cancelled like regular offers
- Expired listings and offers are automatically filtered out from the display
- Some listings or offers may appear even if sold/cancelled/accepted, as only expiry date can be checked - transactions will fail for those

