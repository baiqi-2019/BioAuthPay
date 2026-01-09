# BioAuthPay - Biometric Smart Payment Authorization System

An AI agent payment authorization solution based on device-native security, integrating EIP-7951 and HTTP 402 protocols to make AI payments more secure and convenient.

## Project Overview

BioAuthPay is an innovative AI agent payment authorization system that perfectly combines biometric technology, device-native security chips, and blockchain payments. Users authorize payment limits through device-native biometric authentication (fingerprint, Face ID, or Windows Hello), enabling AI agents to automatically complete micropayments within the authorized scope without repeated confirmations, significantly enhancing the user experience and security of AI-automated payments.

## Main Features

- **Device-Native Security**: Private keys are stored in device security chips (Secure Enclave/TEE) and never leave the device
- **Biometric Authorization**: Supports multiple biometric methods including fingerprint, Face ID, and Windows Hello
- **Smart Authorization Policy**: One-time authorization for multiple uses; micropayments execute automatically, while large payments require re-authorization
- **HTTP 402 Integration**: Perfect support for HTTP 402 Payment Required protocol, enabling seamless paid access to web resources
- **EIP-7951 Standard**: Adopts secp256r1 elliptic curve signatures, perfectly compatible with modern device security standards
- **On-Chain Audit Trail**: All payment records are permanently stored on the blockchain, queryable and verifiable

## Project Links

- **GitHub**: [https://github.com/yourusername/BioAuthPay](https://github.com/yourusername/BioAuthPay)
- **Live Demo**: [http://localhost:3000](http://localhost:3000)

## Achievements and Highlights

- **Innovative Integration**: Combines EIP-7951 device-native security standards with HTTP 402 payment protocol, pioneering a new model for Web3 payments
- **Production-Ready**: Solves the conflict between security and convenience in AI agent automated payments with a production-grade solution
- **User-Friendly**: No need to remember complex private keys; authorization via fingerprint or face recognition lowers the barrier to Web3 adoption
- **Secure and Controllable**: Supports flexible authorization policy configuration, allowing users to customize single-transaction thresholds and total authorization limits

## Team

- **Developer**: [Andy]
- **Role**: Full-Stack Development / Product Design
- **Contact**: tdcq532787678@gmail.com

## One-Sentence Explanation

BioAuthPay enables AI agents to complete payments as securely and conveniently as humans - authorize once with biometrics, and AI automatically handles multiple micropayments, like giving AI a "fingerprint-enabled credit card"!

## What Problems Do We Solve?

### Problem One: Security Dilemma of AI Agent Payments

**Traditional Approach**: AI agents need access to user private keys to initiate payments, posing serious security risks.

**Our Solution**: Private keys never leave the device security chip; AI agents can only make payments within the user's biometrically-authorized limit, ensuring both security and automation.

### Problem Two: Requiring User Confirmation for Every Payment Creates Poor Experience

**Traditional Approach**: Every micropayment requires users to open their wallet, enter passwords, and confirm transactions, disrupting workflows.

**Our Solution**: One-time biometric authorization enables AI to automatically complete multiple payments within the authorized limit; re-authorization is only needed when thresholds are exceeded.

### Problem Three: Fragmented Experience for Paid Web Resource Access

**Traditional Approach**: Accessing paid content requires registration, card binding, recharge, and subscription - a complex process.

**Our Solution**: Through HTTP 402 protocol, AI automatically handles payments when detecting paid content, allowing users to access content seamlessly with true "pay-as-you-go" functionality.

## How Core Technologies Make This Possible?

### EIP-7951: Device-Native Security

EIP-7951 allows smart contracts to directly verify secp256r1 signatures from device security chips. This means:

1. **Private Keys Generated in Security Chips**: iOS Secure Enclave, Android TEE, Windows TPM, etc.
2. **Private Keys Never Exported**: Hardware-level protection; even rooted devices cannot extract keys
3. **Biometric Required for Each Signature**: Fingerprint, Face ID, etc., preventing unauthorized use
4. **On-Chain Verifiable**: Smart contracts can directly verify signature validity without trusting third parties

### HTTP 402: Payment Required

HTTP 402 is a status code specifically designed for web resource payments. In our system:

1. **Resource Protection**: Server returns 402 response, indicating payment required
2. **Automatic Processing**: AI agent detects 402 and automatically pays from authorized limit
3. **Obtain Credentials**: After payment completion, receive blockchain transaction hash as proof
4. **Access Resources**: Re-request with payment credentials to obtain protected content

### Smart Authorization Policy

We designed a flexible authorization policy system:

- **Total Authorization Limit**: User authorizes total amount in one go (e.g., 1000 USDC)
- **Single Payment Threshold**: Payments exceeding this amount require re-authorization (e.g., 500 USDC)
- **Automatic Deduction**: Qualifying payments execute automatically without user confirmation
- **Limit Tracking**: Real-time display of used and remaining limits
- **Flexible Configuration**: Users can adjust authorization policies anytime

## Core Features

### Multi-Device Biometric Support

- **iOS Devices**: Face ID / Touch ID
- **Android Devices**: Fingerprint Recognition / Facial Recognition
- **Windows**: Windows Hello (Fingerprint/Face/Iris)
- **macOS**: Touch ID

All biometric operations are completed within the device secure area, with third-party applications unable to access biometric data.

### Flexible Authorization Policies

- **Total Limit Control**: Set maximum total amount for one-time authorization
- **Single Transaction Threshold**: Configure automatic execution limit for single payments
- **Limit Tracking**: Real-time display of used and remaining limits
- **Automatic Reminders**: Alert users when limit is about to be exhausted
- **Immediate Effect**: Authorization configuration changes take effect immediately

### HTTP 402 Resource Protection

- **Standard Protocol**: Based on HTTP 402 Payment Required standard
- **Resource Configuration**: Service providers can flexibly configure resource prices
- **Automatic Payment**: AI automatically processes payment upon detecting 402 response
- **Seamless Access**: Transparently obtain protected content after payment completion
- **On-Chain Credentials**: Each payment has an on-chain transaction hash as proof

### Complete Audit Trail

- **Payment Records**: Complete information for each payment permanently stored
- **Authorization History**: All authorization operations are traceable
- **Signature Verification**: Support verification of each signature's validity
- **Blockchain Explorer**: Query transactions on blockchain explorer
- **Compliance Audit**: Meets regulatory audit requirements

## Technical Implementation

### Frontend Tech Stack

- **Framework**: Next.js 16.1.0 (App Router + Turbopack)
- **UI Library**: React 19.2.3 + shadcn/ui + Tailwind CSS 4
- **State Management**: Zustand 5.0.9
- **Icons**: Lucide React
- **Language**: TypeScript 5

### Core Modules

- **Payment Authorization Console** (`app/page.tsx`):
  - Three-step payment flow display
  - AI request generation and payment details display
  - Real-time system log monitoring

- **Authorization Management Backend** (`app/admin/page.tsx`):
  - Authorization limit configuration
  - Single payment threshold settings
  - Usage statistics display

- **402 Resource Configuration** (`app/admin/402-config/page.tsx`):
  - Protected resource configuration
  - Payment amount and recipient address settings
  - Blockchain network selection

- **State Management** (`lib/store.ts`):
  - Payment flow state management
  - Authorization policy engine
  - Smart payment decision logic

- **Biometric Component** (`components/BioAuthModal.tsx`):
  - Universal biometric authorization modal
  - Multi-device type simulation
  - Authorization success callback handling

### API Design

- **GET /api/resources/[id]**: Protected resource access interface
  - Returns 402 status without payment credentials
  - Returns protected content with credentials
  - Supports multiple resource types

## Application Scenarios

### AI Subscription Service Auto-Renewal

AI agents detect upcoming expiration of subscription services like Netflix and Spotify, automatically completing renewals within the authorized limit without manual user intervention.

### AI Content Creation Paid Assets

When AI creates content requiring paid assets (images, music, fonts, etc.), it automatically completes micropayments and obtains usage rights.

### Enterprise AI Service Invocation

Enterprises configure authorization limits for AI assistants, enabling automatic invocation of various API services (translation, analysis, data queries, etc.) to improve work efficiency.

### Decentralized Application Micropayments

DApp users authorize once, and various small operations within the app (sending messages, creating content, voting, etc.) automatically complete payments, enhancing user experience.

## Project Architecture

```
┌─────────────────────┐
│   User Interface    │
│  - Payment Console  │
│  - Admin Backend    │
│  - 402 Config       │
└──────────┬──────────┘
           │
┌──────────▼──────────┐
│   Business Logic    │
│  - Zustand Store    │
│  - Auth Policy      │
│  - Payment Control  │
└──────────┬──────────┘
           │
┌──────────▼──────────┐
│  Security Layer     │
│  - EIP-7951 Sign    │
│  - Biometric Auth   │
│  - Security Chip    │
└──────────┬──────────┘
           │
┌──────────▼──────────┐
│  Blockchain Layer   │
│  - Smart Contract   │
│  - On-Chain Storage │
│  - TX Verification  │
└─────────────────────┘
```

## Quick Start

### Install Dependencies

```bash
npm install
```

### Start Development Server

```bash
npm run dev
```

Visit [http://localhost:3000](http://localhost:3000) to view the application

### Project Structure

```
BioAuthPay/
├── app/                    # Next.js App Router
│   ├── page.tsx           # Payment authorization console homepage
│   ├── admin/             # Authorization management backend
│   │   ├── page.tsx       # Authorization configuration page
│   │   └── 402-config/    # 402 resource configuration
│   └── api/               # API routes
│       └── resources/     # Protected resource interface
├── components/            # React components
│   ├── ui/               # shadcn/ui components
│   └── BioAuthModal.tsx  # Biometric authorization modal
├── lib/                   # Utility library
│   └── store.ts          # Zustand state management
├── public/               # Static assets
├── README.md             # Project documentation
├── prompts.md            # AI prompts log
└── demo.md               # Demo documentation
```

## Project Advantages

- **Security**: Private keys never leave device, biometric protection for each signature
- **Convenience**: One-time authorization for multiple uses, AI automated payments
- **Flexibility**: Configurable authorization policies for different scenarios
- **Transparency**: All payments on-chain and queryable, complete audit trail
- **Standardization**: Based on EIP-7951 and HTTP 402 standards, easy to integrate
- **User-Friendly**: No need to understand blockchain technology, just use familiar biometric authentication

## Future Roadmap

### Multi-Chain Support
- Support for Ethereum, Polygon, Arbitrum, and other chains
- Cross-chain payments and asset bridging
- Unified authorization limit management

### Social Recovery
- Key recovery mechanism based on social relationships
- Multi-device authorization management
- Inheritance mechanism

### AI Autonomous Decision-Making
- Machine learning-based payment decision optimization
- Smart budget management and recommendations
- Anomalous payment behavior detection and alerts

### Ecosystem Expansion
- Developer SDK to simplify integration process
- Service marketplace connecting payers and service providers
- DAO governance, with community determining platform development direction

## Related Documentation

- [AI Prompts Log](./prompts.md) - Records key AI prompts used during development
- [Demo Documentation](./demo.md) - Contains demo links, screenshots, and usage instructions

## License

MIT License

---

**BioAuthPay** - Making AI payments as simple and secure as fingerprint unlock!
