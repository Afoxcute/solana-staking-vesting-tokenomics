# Solana Staking & Vesting Tokenomics

A comprehensive Solana-based staking and token vesting platform that enables token locking, staking with rewards, and scheduled token distribution.

## Project Structure

The repository contains several key components:

1. **No1ZET-platform-frontend** - React-based web interface for interacting with the platform
   - Built with Vite + React
   - Styled with Tailwind CSS
   - Implements wallet connection and smart contract interactions
   - Responsive design for desktop and mobile

2. **solana-token-staking** - Core staking program implementation
3. **solana-token-vesting** - Token vesting and distribution program
4. **solana-NFT-staking** - NFT staking functionality
5. **z01zet-tokenomics-contract** - Main tokenomics contract implementation

## Features

### 1. Token Staking Program
- Stake tokens to earn rewards based on APY
- Support for multiple staking pools with different reward rates
- Referral reward system
- Compound rewards functionality
- Fee mechanism for staking operations

### 2. Token Vesting Program
- Time-locked token vesting with cliff periods
- Linear vesting schedule
- Support for multiple vesting schedules per user
- Emergency withdrawal functionality
- Reward distribution based on vesting schedule

### 3. NFT Staking (WIP)
- NFT staking functionality
- Reward distribution for NFT stakers
- Integration with SPL tokens for rewards

## Smart Contracts

### Staking Program (`solana-spltoken-staking`)
- **create_pool**: Initialize a new staking pool with custom APY and fees
- **stake**: Stake tokens into a pool
- **unstake**: Withdraw staked tokens
- **claim**: Claim staking rewards
- **compound**: Compound earned rewards back into the staking pool

### Vesting Program (`solana-spltoken-vesting`)
- **create_state**: Initialize the vesting program state
- **create_pool**: Create a new vesting pool
- **vest**: Lock tokens into the vesting schedule
- **unvest**: Withdraw tokens according to the vesting schedule
- **harvest**: Claim vested tokens

## Security Features
- Access control with program-derived addresses (PDAs)
- Secure token transfers using Anchor framework
- Input validation and error handling
- Time-based vesting with proper time calculations

## Frontend Application

The No1ZET platform frontend is a modern React application that provides a user-friendly interface for interacting with the Solana staking and vesting programs.

### Key Features

- **Wallet Integration**
  - Connect with popular Solana wallets (Phantom, Solflare, etc.)
  - Display wallet balance and connected network
  - Handle transaction signing and confirmation

- **Staking Interface**
  - View available staking pools with APY and other metrics
  - Stake/Unstake tokens with a few clicks
  - Track staking rewards in real-time
  - Compound rewards functionality

- **Vesting Dashboard**
  - View vesting schedules and unlock dates
  - Claim vested tokens
  - Track vesting progress with visual indicators

- **NFT Staking** (Coming Soon)
  - View staked NFTs
  - Track rewards for NFT staking
  - Manage NFT positions

### Development Setup

1. Navigate to the frontend directory:
   ```bash
   cd No1ZET-platform-frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   ```

3. Configure environment variables:
   Create a `.env` file in the frontend root with the following variables:
   ```
   VITE_RPC_ENDPOINT=your_rpc_endpoint
   VITE_STAKING_PROGRAM_ID=your_staking_program_id
   VITE_VESTING_PROGRAM_ID=your_vesting_program_id
   ```

4. Start the development server:
   ```bash
   npm run dev
   # or
   yarn dev
   ```

### Building for Production

```bash
npm run build
# or
yarn build
```

### Deployment

The frontend can be deployed to various platforms:
- Vercel (recommended)
- Firebase Hosting
- Netlify
- Any static hosting service

## Development

### Prerequisites
- Rust (latest stable version)
- Solana CLI tools
- Anchor framework
- Node.js and npm/yarn (for tests and deployment)

### Building

```bash
# Build all programs
cd solana-token-staking/programs/solana-spltoken-staking
cargo build-bpf

cd ../../..
cd solana-token-vesting/programs/solana-spltoken-vesting
cargo build-bpf
```

### Testing

Run the test suite using:

```bash
anchor test
```

## Deployment

1. Configure your Solana CLI:
   ```bash
   solana config set --url <cluster-url>
   solana config set --keypair ~/.config/solana/id.json
   ```

2. Deploy the programs:
   ```bash
   anchor deploy
   ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Security

Please report any security issues or concerns to the project maintainers.

## Disclaimer

This software is provided "as is" without warranty of any kind. Use at your own risk.
