# Alignment Node Delegator - 0G Network

A web application for managing NFT delegations on the 0G-Galileo-Testnet (Arbitrum). This application allows users to delegate and undelegate their NFTs to operators through a user-friendly interface.

## Features

- 🔗 **Wallet Connection**: Connect via MetaMask or other Web3 wallets
- 🎯 **NFT Delegation**: Delegate multiple NFTs to operators
- 🔄 **NFT Undelegation**: Undelegate NFTs from operators
- 📊 **Delegation Status**: Check current delegation status
- ✅ **NFT Approval**: Approve contracts to manage your NFTs
- 🌐 **Network Support**: Automatically switches to Arbitrum One

## Prerequisites

- MetaMask or another Web3-compatible browser wallet
- NFTs on the Arbitrum One network
- ETH for transaction fees

## Docker Deployment

### Option 1: Using Docker Compose (Recommended)

1. **Clone or download the project files**

2. **Build and run with Docker Compose:**
   ```bash
   docker-compose up -d
   ```

3. **Access the application:**
   Open your browser and navigate to: `http://localhost:8080`

4. **Stop the application:**
   ```bash
   docker-compose down
   ```

### Option 2: Using Docker directly

1. **Build the Docker image:**
   ```bash
   docker build -t delegation-checker .
   ```

2. **Run the container:**
   ```bash
   docker run -d -p 8080:80 --name delegation-checker-app delegation-checker
   ```

3. **Access the application:**
   Open your browser and navigate to: `http://localhost:8080`

4. **Stop and remove the container:**
   ```bash
   docker stop delegation-checker-app
   docker rm delegation-checker-app
   ```

## Usage

1. **Connect Your Wallet**
   - Click "Connect Wallet" and approve the connection in MetaMask
   - The app will automatically switch to Arbitrum One if needed

2. **Approve NFTs (First Time Only)**
   - If prompted, click "Approve All NFTs" to allow the contract to manage your NFTs
   - This is a one-time approval per wallet

3. **Delegate NFTs**
   - Enter the operator's address
   - Enter token IDs (comma-separated, e.g., "1, 2, 3, 4")
   - Click "Delegate NFTs"

4. **Check Delegation Status**
   - Enter an operator's address
   - Click "Check Delegation" to see which tokens are delegated

5. **Undelegate NFTs**
   - Enter the operator's address
   - Enter token IDs to undelegate
   - Click "Undelegate NFTs"

## Configuration

The application is configured for:
- **Network**: Arbitrum One (Chain ID: 42161)
- **NFT Contract**: `0xd0f4E1265Edd221b5bb0e8667a59f31B587B2197`
- **Manager Contract**: `0xdD158B8A76566bC0c342893568e8fd3F08A9dAac`

To modify these settings, edit the constants in `app.js`:
```javascript
const CONTRACT_ADDRESS = '0xdD158B8A76566bC0c342893568e8fd3F08A9dAac';
const NFT_CONTRACT_ADDRESS = '0xd0f4E1265Edd221b5bb0e8667a59f31B587B2197';
const CHAIN_ID = 42161;
```

## Development

For local development without Docker:

1. Serve the files using a local web server:
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js (if you have http-server installed)
   npx http-server -p 8000
   ```

2. Access the application at `http://localhost:8000`

## Architecture

- **Frontend**: Vanilla HTML, CSS, and JavaScript
- **Web3 Integration**: Web3.js library for blockchain interactions
- **Styling**: Custom CSS with dark theme
- **Hosting**: Nginx in Docker container

## Security Features

- HTTPS-ready configuration
- Security headers (X-Frame-Options, X-Content-Type-Options, etc.)
- Input validation for addresses and token IDs
- Contract approval checks before transactions

## Troubleshooting

- **Wallet Connection Issues**: Ensure MetaMask is installed and unlocked
- **Network Errors**: Verify you're connected to Arbitrum One
- **Transaction Failures**: Check you have sufficient ETH for gas fees
- **NFT Not Found**: Verify the token IDs exist and you own them

## Support

For issues or questions related to the 0G Network delegation system, please refer to the official 0G Network documentation and community channels.
