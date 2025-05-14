# Etherscan Priority Fee Calculator

A Tampermonkey userscript that enhances Etherscan transaction pages by displaying actual Priority Fee (tips) calculations for EIP-1559 transactions.

## Features

- Real-time Priority Fee calculation for EIP-1559 transactions
- Displays fees in both Gwei and ETH units
- Clean and intuitive UI integration with Etherscan
- Supports all Etherscan subdomains
- Automatic calculation upon page load

## Installation

1. Install the [Tampermonkey](https://www.tampermonkey.net/) browser extension
2. Click on the Tampermonkey icon and select "Create a new script"
3. Copy the entire content of `etherscan_priority_fee.user.js` into the editor
4. Save the script (Ctrl+S or Command+S)

Alternatively, you can:
1. Install Tampermonkey
2. Visit the [script homepage](https://github.com/yuouiu/etherscan-priority-fee-calculator)
3. Click on the raw script file to trigger Tampermonkey's automatic installation

## Usage

1. Visit any Ethereum transaction page on Etherscan (e.g., https://etherscan.io/tx/[transaction-hash])
2. The script will automatically calculate and display the actual Priority Fee below the transaction title
3. The fee will be shown in both Gwei and ETH units for convenience

## Technical Implementation

The script works by:
1. Fetching transaction data using JSON-RPC calls
2. Retrieving block data and transaction receipts
3. Calculating the actual Priority Fee using the formula:
   ```javascript
   actualPriorityFee = min(maxPriorityFeePerGas, maxFeePerGas - baseFeePerGas) * gasUsed
   ```
4. Converting values between Wei, Gwei, and ETH units
5. Displaying results in a clean, styled container on the page

## API Endpoint

The script uses `https://eth.blockrazor.xyz` as the JSON-RPC endpoint for fetching blockchain data. This is a public endpoint and may have rate limits.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Support

For issues, feature requests, or contributions, please visit the [GitHub repository](https://github.com/yuouiu/etherscan-priority-fee-calculator).
