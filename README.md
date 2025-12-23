# Sonic Marketplace - Cancel Listings & Offers Tool

A standalone HTML tool for managing and canceling NFT listings and offers on the Sonic network marketplace.

## Features

- **Wallet Connection**: Connect to MetaMask or other Web3 wallets, automatically switches to Sonic network (Chain ID: 146)
- **Fetch Listings**: Retrieves all listings from the marketplace using Etherscan API v2 with pagination support
- **Fetch Offers**: Retrieves all offers from the marketplace using Etherscan API v2 with pagination support
- **Event Filtering**: Filters `NewListing` and `NewOffer` events to extract marketplace IDs and offer IDs
- **Single Cancellation**: Cancel individual listings or offers by clicking their ID buttons
- **Batch Cancellation**: Select multiple listings or offers with checkboxes and cancel them all at once

## Usage

1. Open `index.html` in a web browser
2. Click "Connect Wallet" and approve the connection in your wallet
3. Enter your Etherscan API key
4. **For Listings**:
   - Click on the "Listings" tab (default)
   - Click "Fetch All Listings" to retrieve all listings
   - Cancel listings individually or select multiple and use "Cancel Selected Listings"
5. **For Offers**:
   - Click on the "Offers" tab
   - Click "Fetch All Offers" to retrieve all offers
   - Cancel offers individually or select multiple and use "Cancel Selected Offers"

## Configuration

- **Marketplace Contract**: `0x0c558365eeff4b057fdbed91bc3650e1a00018b4`
- **Network**: Sonic (Chain ID: 146)
- **Event Signatures**:
  - `0x217bd5b40e04ee284d8ebf246fe31b6cf1b5aa0fc343ce0ef5325ee90ef40bea` (NewListing event)
  - `0x51ddc3ce4e6137c19b8b4521871ae05623a9c72df697faf2fdfd1b1a639170b3` (NewOffer event)

## Requirements

- Modern web browser with Web3 wallet extension (MetaMask recommended)
- Etherscan API key (get one at https://etherscan.io/apis)
- Internet connection

## Notes

- The tool uses Etherscan API v2 format with `chainid=146` for Sonic network
- Listings and offers are sorted by ID (latest first)
- The tool filters for `NewListing` and `NewOffer` events specifically
- Expired listings and offers are automatically filtered out from the display
- Some listings or offers may appear even if sold/cancelled/accepted, as only expiry date can be checked - transactions will fail for those

