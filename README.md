# 💰 CoinPay - Cryptocurrency Payment Gateway

A modern, secure cryptocurrency payment gateway built with Next.js and WalletConnect. Send ETH payments seamlessly with a beautiful, responsive UI.

![Next.js](https://img.shields.io/badge/Next.js-14-black)
![React](https://img.shields.io/badge/React-18-blue)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.3-38bdf8)
![WalletConnect](https://img.shields.io/badge/WalletConnect-v2-3b99fc)

## 🚀 Features

### Core Functionality
- **🔗 Wallet Connection**: Connect your crypto wallet using WalletConnect protocol
- **💸 Payment Processing**: Send Ethereum (ETH) payments to any address
- **📊 Transaction Tracking**: Real-time transaction status with Etherscan links
- **🔄 Live Updates**: Monitor wallet connection status and chain changes

### User Experience
- **🎨 Modern UI**: Beautiful, clean interface built with Tailwind CSS
- **🌙 Dark Mode**: Automatic dark mode support based on system preferences
- **📱 Responsive**: Fully optimized for mobile, tablet, and desktop
- **⚡ Fast**: Optimized performance with Next.js App Router
- **✨ Smooth Animations**: Loading states and transitions for better UX

## 🛠️ Tech Stack

- **Framework**: [Next.js 14](https://nextjs.org/) (App Router)
- **UI Library**: [React 18](https://react.dev/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **Wallet Integration**: [WalletConnect v2](https://walletconnect.com/)
- **Blockchain**: [Ethers.js v6](https://docs.ethers.org/)
- **Language**: JavaScript (ES6+)

## 📋 Prerequisites

Before you begin, ensure you have:

- **Node.js** 18.0 or higher
- **npm** or **yarn** package manager
- **WalletConnect Project ID** (Get one free at [cloud.walletconnect.com](https://cloud.walletconnect.com))

## 🔧 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/coinpay.git
   cd coinpay
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up environment variables**
   
   Create a `.env.local` file in the root directory:
   ```bash
   cp .env.example .env.local
   ```
   
   Add your WalletConnect Project ID:
   ```env
   NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID=your_project_id_here
   NEXT_PUBLIC_CHAIN_ID=1
   ```
   
   > **Note**: 
   > - `NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID`: Get your Project ID from [WalletConnect Cloud](https://cloud.walletconnect.com)
   > - `NEXT_PUBLIC_CHAIN_ID`: Network chain ID (1 = Ethereum Mainnet, 5 = Goerli Testnet)

4. **Run the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

5. **Open your browser**
   
   Navigate to [http://localhost:3000](http://localhost:3000)

## 📁 Project Structure

```
coinpay/
├── app/                    # Next.js App Router directory
│   ├── api/               # API routes
│   │   └── payment/       # Payment API endpoints
│   ├── globals.css        # Global styles with Tailwind
│   ├── layout.js          # Root layout component
│   └── page.js            # Home page (payment gateway)
│
├── components/            # React components
│   ├── WalletConnect.js   # Wallet connection component
│   ├── PaymentForm.js     # Payment form with validation
│   ├── PaymentStatus.js   # Transaction status display
│   └── TransactionHistory.js # Transaction history (future)
│
├── lib/                   # Utility libraries
│   ├── walletconnect.js   # WalletConnect initialization & methods
│   └── payment.js         # Payment utilities (future)
│
├── public/                # Static assets
│   └── walletconnect.svg  # WalletConnect logo
│
├── next.config.js         # Next.js configuration
├── tailwind.config.js     # Tailwind CSS configuration
├── postcss.config.js      # PostCSS configuration
└── package.json           # Project dependencies
```

## 🎯 Usage

### Connecting Your Wallet

1. Click the **"Connect Wallet"** button
2. A QR code will appear for mobile wallet scanning
3. Scan with your mobile wallet app (MetaMask, Trust Wallet, etc.)
4. Approve the connection on your wallet
5. Your wallet address will be displayed once connected

### Sending Payments

1. **Ensure your wallet is connected**
2. **Enter recipient address** in the "Recipient Address" field
3. **Enter amount** in ETH (e.g., `0.1` for 0.1 ETH)
4. **Click "Send Payment"**
5. **Approve the transaction** in your wallet
6. **View transaction hash** and Etherscan link once confirmed

### Viewing Transactions

- Transaction hash is displayed after successful payment
- Click the Etherscan link to view transaction details on the blockchain
- Transaction status updates in real-time

## 🔐 Security

### Best Practices
- **No Private Key Storage**: Private keys never leave your wallet - all operations use WalletConnect
- **Client-Side Processing**: All wallet operations are performed entirely client-side
- **Environment Variables**: Sensitive configuration stored securely in `.env.local` (gitignored)
- **Transaction Validation**: All transactions are validated before sending
- **Error Handling**: Comprehensive error handling for failed transactions

### Wallet Security
- Always verify transaction details before approving
- Only connect to trusted applications
- Never share your wallet's private key or seed phrase
- Double-check recipient addresses before sending

## 🌐 Supported Networks

Currently configured for:
- **Ethereum Mainnet** (Chain ID: 1) - Default

To change networks, update `NEXT_PUBLIC_CHAIN_ID` in `.env.local`:
- **Goerli Testnet**: `5`
- **Sepolia Testnet**: `11155111`
- **Polygon Mainnet**: `137`
- **BNB Smart Chain**: `56`

## 🧪 Testing

### Development Testing

1. **Use a Testnet**: Set `NEXT_PUBLIC_CHAIN_ID=5` for Goerli testnet
2. **Get Test ETH**: Request from [Goerli Faucet](https://goerlifaucet.com/)
3. **Test Transactions**: Send test transactions without spending real money

### Manual Testing Checklist

- [ ] Wallet connects successfully
- [ ] Wallet address displays correctly
- [ ] Chain ID displays correctly
- [ ] Payment form validates inputs
- [ ] Transactions send successfully
- [ ] Transaction hash displays after sending
- [ ] Etherscan link works correctly
- [ ] Error messages display for failed transactions
- [ ] UI is responsive on mobile devices
- [ ] Dark mode works correctly

## 🚀 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Import your repository on [Vercel](https://vercel.com)
3. Add environment variables in Vercel dashboard
4. Deploy!

### Other Platforms

The app can be deployed to any platform that supports Next.js:
- **Netlify**
- **AWS Amplify**
- **Railway**
- **Self-hosted server**

Make sure to set environment variables on your deployment platform.

## 📝 Available Scripts

```bash
# Development server
npm run dev

# Production build
npm run build

# Start production server
npm start

# Lint code
npm run lint
```

## 🔮 Future Enhancements

- [ ] Transaction history persistence
- [ ] Multiple token support (ERC-20 tokens)
- [ ] Payment notifications
- [ ] Multi-chain support with chain switching
- [ ] Payment templates/favorites
- [ ] Batch payments
- [ ] QR code scanning for recipient addresses
- [ ] Payment scheduling
- [ ] Export transaction history

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- [WalletConnect](https://walletconnect.com/) for the amazing wallet connection protocol
- [Next.js](https://nextjs.org/) team for the excellent framework
- [Tailwind CSS](https://tailwindcss.com/) for the utility-first CSS framework
- [Ethers.js](https://docs.ethers.org/) for Ethereum interaction utilities

## 📞 Support

If you encounter any issues or have questions:

- Open an issue on [GitHub](https://github.com/yourusername/coinpay/issues)
- Check the [WalletConnect Documentation](https://docs.walletconnect.com/)
- Review [Next.js Documentation](https://nextjs.org/docs)

---

**Built with ❤️ using Next.js and WalletConnect**

