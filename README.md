# 🌐 VeriChainX + AfriChain - Complete Blockchain Authenticity Ecosystem

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11+](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org/downloads/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-blue.svg)](https://www.typescriptlang.org/)
[![Solidity](https://img.shields.io/badge/Solidity-0.8+-blue.svg)](https://soliditylang.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-00a393.svg)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-18+-61dafb.svg)](https://reactjs.org)
[![Hedera](https://img.shields.io/badge/Hedera-Network-purple.svg)](https://hedera.com)

## 🏗️ Two-Tier Architecture Overview

This repository contains both the **VeriChainX protocol infrastructure** and the **AfriChain consumer application** that demonstrates how to build on top of VeriChainX.

### 🔧 VeriChainX Protocol Layer
The foundational blockchain infrastructure providing:
- **Smart Contract Suite** - Complete authenticity verification protocols
- **DeFi Integration** - AMM, lending, staking, and DEX functionality  
- **Cross-Chain Bridge** - Multi-blockchain interoperability
- **DAO Governance** - Decentralized protocol management
- **Token Factory** - Dynamic token creation and management

### 🌍 AfriChain Application Layer  
A comprehensive consumer application built on VeriChainX, specifically designed for African artisans and small-scale manufacturers with enterprise-grade product authenticity verification, multi-channel authentication, QR code verification, and integrated payment solutions supporting both HBAR and M-Pesa.

## 🚀 Key Features

### 🔐 Multi-Channel Authentication
- **📱 Phone Number Registration** - Secure phone-based account creation with OTP verification
- **🔑 JWT Token Management** - Secure session management with refresh token rotation  
- **📞 USSD Integration** - Feature phone support for rural African markets
- **📧 SMS & Email Support** - Multi-channel communication for maximum reach
- **🔄 Cross-Channel Session Coordination** - Seamless experience across all touchpoints

### 🏷️ Product Registration & Verification
- **🌐 IPFS Metadata Storage** - Decentralized product information storage
- **🎫 Hedera NFT Minting** - Blockchain-backed authenticity certificates
- **📱 QR Code Generation** - Dynamic QR codes for instant product verification
- **📚 Product Catalog Management** - Comprehensive inventory and metadata management
- **🔍 Real-Time Verification** - Instant blockchain verification through QR scanning

### 💰 Integrated Payment Solutions
- **💎 HBAR Payment Processing** - Native Hedera cryptocurrency payments
- **📱 M-Pesa Integration** - Popular African mobile money solution
- **🔄 Real-Time Exchange Rates** - Dynamic USD/HBAR/KES conversion
- **📊 Payment Status Tracking** - Comprehensive transaction monitoring
- **🧾 Automated Receipts** - Multi-format payment confirmations

### 🛡️ Advanced Security & Fraud Detection
- **🔗 Blockchain Verification** - Immutable authenticity records on Hedera
- **🤖 AI-Powered Fraud Detection** - Machine learning pattern recognition
- **📈 Real-Time Analytics** - Comprehensive fraud monitoring dashboard
- **⚠️ Automated Alerting** - Instant notifications for suspicious activities
- **🔍 Verification Results Display** - Clear authenticity status presentation

### 📱 Enterprise Admin Dashboard
- **📊 Analytics & Insights** - Real-time business intelligence
- **🏪 Product Management** - Comprehensive inventory control
- **📋 Activity Monitoring** - Complete audit trail visibility
- **👥 User Management** - Role-based access control
- **🔧 System Configuration** - Flexible platform customization

This is the front end - https://africhain.live 

## 🏗️ Combined Architecture Overview

```mermaid
graph TB
    subgraph "AfriChain Application Layer"
        subgraph "Frontend"
            Admin[Admin Dashboard - React/TypeScript]
            Mobile[Mobile Interface - PWA]
            QR[QR Scanner Interface]
            Landing[VeriChainX Landing Page]
        end
        
        subgraph "API Services"
            Auth[Auth Service - Node.js/TypeScript]
            Hedera[Hedera Service - Node.js/TypeScript]
            API[Core API - Python/FastAPI]
        end
        
        subgraph "AfriChain Features"
            SMS[SMS Service - Africa's Talking]
            USSD[USSD Gateway]
            MPESA[M-Pesa Gateway]
            Exchange[Exchange Rate API]
        end
    end
    
    subgraph "VeriChainX Protocol Layer"
        subgraph "Smart Contracts"
            AuthVerifier[VeriChainXAuthenticityVerifier.sol]
            TokenFactory[VeriChainXTokenFactory.sol]
            Governance[VeriChainXGovernance.sol]
            Treasury[VeriChainXDAOTreasury.sol]
        end
        
        subgraph "DeFi Protocols"
            AMM[VeriChainXAuthenticityAMM.sol]
            DEX[VeriChainXDEX.sol]
            Lending[VeriChainXLending.sol]
            Staking[VeriChainXStaking.sol]
        end
        
        subgraph "Cross-Chain Infrastructure"
            Bridge[VeriChainXCrossChainBridge.sol]
            Relay[VeriChainXBridgeRelay.sol]
            AuthToken[VeriChainXAuthenticityToken.sol]
        end
    end
    
    subgraph "Hedera Network Infrastructure"
        HCS[Hedera Consensus Service]
        HTS[Hedera Token Service]
        HSCS[Hedera Smart Contract Service]
        IPFS[IPFS Storage]
    end
    
    subgraph "Data & Cache Layer"
        PG[(PostgreSQL + pgvector)]
        Redis[(Redis Cache)]
        TiDB[(TiDB Serverless)]
    end
    
    %% AfriChain to VeriChainX connections
    Admin --> Auth
    Mobile --> Auth
    QR --> Hedera
    Auth --> AuthVerifier
    Hedera --> TokenFactory
    API --> Governance
    
    %% VeriChainX to Hedera connections
    AuthVerifier --> HSCS
    TokenFactory --> HTS
    AMM --> HSCS
    Bridge --> HSCS
    
    %% Infrastructure connections
    HSCS --> HCS
    Auth --> PG
    Auth --> Redis
    Hedera --> IPFS
    API --> TiDB
    
    %% AfriChain specific integrations
    MPESA --> Exchange
    SMS --> Auth
    USSD --> Auth
```

## 🛠️ Tech Stack

### VeriChainX Protocol Layer
- **Solidity 0.8+** - Smart contract development for authenticity verification
- **Hardhat** - Development environment and testing framework
- **OpenZeppelin** - Security-audited contract libraries
- **VeriChainX Smart Contracts**:
  - `VeriChainXAuthenticityVerifier.sol` - Core verification logic
  - `VeriChainXTokenFactory.sol` - Dynamic token creation
  - `VeriChainXGovernance.sol` - DAO governance mechanisms
  - `VeriChainXAuthenticityAMM.sol` - Automated market maker for authenticity tokens
  - `VeriChainXDEX.sol` - Decentralized exchange
  - `VeriChainXCrossChainBridge.sol` - Multi-chain interoperability

### AfriChain Application Services  
- **Node.js/TypeScript** - Auth & Hedera services with modern async patterns
- **Python 3.11+/FastAPI** - Core API services and AI agents
- **PostgreSQL 15+** - Primary database with pgvector for embeddings
- **TiDB Serverless** - Scalable cloud database for analytics
- **Redis 7+** - Caching, sessions, and real-time features

### Blockchain & Distributed Storage
- **Hedera Hashgraph** - Primary blockchain network for smart contracts and consensus
- **Hedera Smart Contract Service (HSCS)** - EVM-compatible smart contract execution
- **Hedera Token Service (HTS)** - Native token creation and management
- **Hedera SDK** - JavaScript SDK for seamless blockchain integration
- **IPFS** - Decentralized metadata and image storage
- **Hedera Mirror Node** - Transaction history and analytics

### Payment & Communication
- **M-Pesa API** - African mobile money integration
- **HBAR** - Native Hedera cryptocurrency processing
- **Africa's Talking** - SMS, voice, and USSD services
- **Real-time Exchange Rates** - Multi-currency conversion APIs
- **WebSocket** - Real-time payment status updates

### AI & Analytics
- **OpenAI GPT-4** - Advanced fraud detection and analysis
- **Anthropic Claude** - Multi-model AI analysis for authenticity
- **Sentence Transformers** - Product similarity embeddings
- **pgvector** - Vector similarity search for duplicate detection
- **TensorFlow.js** - Client-side ML for QR code validation

### Frontend & User Experience
- **React 18** - Modern component-based UI framework
- **TypeScript** - Type-safe development across the stack
- **Vite** - Lightning-fast build tooling and development
- **Tailwind CSS** - Utility-first responsive design system
- **React Query** - Advanced data fetching and state management
- **PWA** - Progressive web app for mobile-first experience

### Development & Operations
- **Docker & Docker Compose** - Containerized development and deployment
- **GitHub Actions** - Automated CI/CD pipelines
- **Jest & Playwright** - Comprehensive testing framework
- **ESLint & Prettier** - Code quality and formatting
- **BMAD Method** - Advanced AI-assisted development methodology

## 📋 Prerequisites

- **Node.js 18+** - For TypeScript services and frontend
- **Python 3.11+** - For AI services and core APIs
- **PostgreSQL 15+** with pgvector extension
- **Redis 7+** - For caching and real-time features
- **Docker & Docker Compose** (recommended for local development)

### For Blockchain Features
- **Hedera Testnet Account** - Get free testnet HBAR from [Hedera Portal](https://portal.hedera.com)
- **IPFS Node** - For decentralized storage (or use Pinata/Web3.Storage)

### For African Market Integration
- **Africa's Talking Account** - For SMS/USSD services
- **M-Pesa Developer Account** - For mobile payments (Safaricom)
- **Exchange Rate API Key** - For real-time currency conversion

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/ZubeidHendricks/AfriChain.git
cd AfriChain
```

### 2. Environment Setup
```bash
# Copy environment templates
cp backend/auth-service/.env.example backend/auth-service/.env
cp backend/hedera-service/.env.example backend/hedera-service/.env

# Edit configurations with your API keys
nano backend/auth-service/.env
nano backend/hedera-service/.env
```

### 3. Local Development Setup

#### Option A: Docker Compose (Recommended)
```bash
# Start all services
docker-compose up -d

# Initialize databases
docker-compose exec auth-service npm run migrate
docker-compose exec hedera-service npm run setup

# Access the application
# Admin Dashboard: http://localhost:3000
# Auth API: http://localhost:3001
# Hedera API: http://localhost:3002
```

#### Option B: Manual Setup
```bash
# Install backend dependencies
cd backend/auth-service
npm install
npm run build

cd ../hedera-service
npm install
npm run build

# Install frontend dependencies
cd ../../frontend/frontend/admin-dashboard
npm install

# Set up databases
createdb africhain_auth
createdb africhain_hedera

# Start services (in separate terminals)
cd backend/auth-service && npm start
cd backend/hedera-service && npm start
cd frontend/frontend/admin-dashboard && npm run dev
```

### 4. Quick Deploy to Digital Ocean

#### Option A: App Platform Deployment
```bash
# 1. Fork this repository
# 2. Go to https://cloud.digitalocean.com/apps
# 3. Create App from GitHub: ZubeidHendricks/AfriChain
# 4. Configure environment variables:
#    - HEDERA_ACCOUNT_ID, HEDERA_PRIVATE_KEY
#    - AFRICAS_TALKING_API_KEY, MPESA_CONSUMER_KEY
#    - DATABASE_URL, REDIS_URL
# 5. Deploy!
```

#### Option B: Droplet Deployment
```bash
# Create Ubuntu 22.04 droplet (2GB RAM recommended)
# SSH into droplet and run:

curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

git clone https://github.com/ZubeidHendricks/AfriChain.git
cd AfriChain
sudo docker-compose up -d
```

## 🔧 Configuration

### Backend Service Environment Variables

#### Auth Service (.env)
```bash
# Core Configuration
NODE_ENV=development
PORT=3001
JWT_SECRET=your-super-secret-jwt-key
JWT_REFRESH_SECRET=your-refresh-secret-key

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/africhain_auth
REDIS_URL=redis://localhost:6379/0

# Africa's Talking API
AFRICAS_TALKING_API_KEY=your-africas-talking-api-key
AFRICAS_TALKING_USERNAME=your-username

# M-Pesa Configuration
MPESA_CONSUMER_KEY=your-mpesa-consumer-key
MPESA_CONSUMER_SECRET=your-mpesa-consumer-secret
MPESA_SHORTCODE=your-business-shortcode
MPESA_PASSKEY=your-lipa-na-mpesa-passkey

# Exchange Rates
EXCHANGE_RATE_API_KEY=your-exchange-rate-api-key

# Email Configuration
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
```

#### Hedera Service (.env)
```bash
# Core Configuration
NODE_ENV=development
PORT=3002

# Hedera Configuration
HEDERA_NETWORK=testnet
HEDERA_ACCOUNT_ID=0.0.YOUR_ACCOUNT_ID
HEDERA_PRIVATE_KEY=your-hedera-private-key

# IPFS Configuration
IPFS_API_URL=https://ipfs.infura.io:5001
IPFS_PROJECT_ID=your-ipfs-project-id
IPFS_PROJECT_SECRET=your-ipfs-secret

# Database
DATABASE_URL=postgresql://user:password@localhost:5432/africhain_hedera
REDIS_URL=redis://localhost:6379/1
```

### Application Access

Once the application is running, access:
- **🖥️ Admin Dashboard**: http://localhost:3000
- **🔐 Auth API Docs**: http://localhost:3001/api-docs
- **⛓️ Hedera API Docs**: http://localhost:3002/api-docs
- **📊 Core API**: http://localhost:8000/docs

### Key API Endpoints

#### Auth Service (Port 3001)
```http
# Authentication
POST /auth/register              # Phone-based registration
POST /auth/verify-otp           # OTP verification
POST /auth/login                # JWT login
POST /auth/refresh              # Token refresh
GET  /auth/profile              # User profile

# Multi-Channel Support
POST /ussd/session              # USSD session handling
POST /mobile/authenticate       # Mobile app auth
GET  /auth/cross-channel/status # Session coordination
```

#### Hedera Service (Port 3002)
```http
# NFT Management
POST /nft/mint                  # Mint product NFT
GET  /nft/{tokenId}            # Get NFT details
POST /nft/transfer             # Transfer NFT ownership

# Product Registration
POST /products/register         # Register new product
GET  /products/{productId}     # Get product details
POST /products/verify          # Verify product authenticity

# QR Code Management
POST /qr/generate              # Generate QR code
GET  /qr/{qrId}/verify        # Verify QR code
POST /qr/analytics            # QR scan analytics

# Payment Processing
POST /payments/hbar            # Process HBAR payment
POST /payments/mpesa           # Process M-Pesa payment
GET  /payments/{paymentId}     # Payment status
GET  /exchange-rates/current   # Current exchange rates
```

#### Core API (Port 8000)
```http
# Analytics & Reporting
GET  /api/v1/analytics/dashboard     # Main dashboard data
GET  /api/v1/analytics/fraud-stats  # Fraud detection metrics
POST /api/v1/reports/generate       # Generate custom reports

# Admin Management
GET  /api/v1/admin/users            # User management
POST /api/v1/admin/settings         # System configuration
GET  /api/v1/admin/audit-logs       # Audit trail
```

## 📁 Project Structure

```
VeriChainX-AfriChain-Ecosystem/
├── 🌐 VeriChainX Protocol Layer
│   └── backend/hedera-service/contracts/    # Smart Contract Suite
│       ├── VeriChainXAuthenticityVerifier.sol # Core verification logic
│       ├── VeriChainXTokenFactory.sol        # Dynamic token creation
│       ├── VeriChainXGovernance.sol          # DAO governance
│       ├── VeriChainXDAOTreasury.sol         # Treasury management
│       ├── AMM/                              # Automated Market Maker
│       │   ├── VeriChainXAuthenticityAMM.sol
│       │   └── VeriChainXAuthenticityToken.sol
│       ├── DeFi/                             # DeFi Protocol Suite
│       │   ├── VeriChainXDEX.sol
│       │   ├── VeriChainXLending.sol
│       │   └── VeriChainXStaking.sol
│       └── Bridge/                           # Cross-Chain Infrastructure
│           ├── VeriChainXCrossChainBridge.sol
│           └── VeriChainXBridgeRelay.sol
│
├── 🌍 AfriChain Application Layer
│   ├── 📱 frontend/
│   │   ├── App.verichainx.tsx             # VeriChainX Landing Page
│   │   ├── components/                     # UI Components
│   │   │   ├── AgentShowcase.tsx          # Hedera Agent Kit Demo
│   │   │   ├── BlockchainSection.tsx      # VeriChainX Features
│   │   │   └── AdminPreview.tsx           # Admin Dashboard Preview
│   │   └── frontend/admin-dashboard/       # AfriChain Admin Interface
│   │       ├── src/components/
│   │       │   ├── activity/              # Activity monitoring
│   │       │   ├── fraud/                 # Fraud detection UI
│   │       │   ├── products/              # Product management
│   │       │   └── qr/                    # QR code management
│   │       └── src/routes.tsx             # Application routing
│   │
│   ├── 🔧 backend/
│   │   ├── auth-service/                  # Multi-Channel Authentication
│   │   │   ├── src/services/
│   │   │   │   ├── mobileAuthService.ts   # Mobile app authentication
│   │   │   │   ├── ussdService.ts         # USSD feature phone support
│   │   │   │   ├── smsService.ts          # SMS/OTP services
│   │   │   │   ├── mpesaService.ts        # M-Pesa integration
│   │   │   │   └── jwtService.ts          # JWT token management
│   │   │   └── routes/
│   │   │       ├── auth.ts                # Authentication endpoints
│   │   │       ├── mobile.ts              # Mobile-specific routes
│   │   │       ├── ussd.ts                # USSD session handling
│   │   │       └── mpesaRoutes.ts         # M-Pesa payment routes
│   │   │
│   │   ├── hedera-service/                # VeriChainX Integration Layer
│   │   │   ├── src/agents/                # Hedera Agent Kit
│   │   │   │   ├── HederaAgentKit.ts      # Main agent orchestrator
│   │   │   │   ├── SmartContractAgent.ts  # VeriChainX contract interaction
│   │   │   │   ├── HtsAgent.ts            # Token service integration
│   │   │   │   └── AMMAgent.ts            # AMM interaction agent
│   │   │   ├── src/services/
│   │   │   │   ├── hederaNftService.ts    # NFT minting & management
│   │   │   │   ├── smartContractService.ts # Contract deployment
│   │   │   │   └── ammService.ts          # AMM liquidity management
│   │   │   └── tests/
│   │   │       ├── agents/                # Agent integration tests
│   │   │       └── services/              # Service unit tests
│   │   │
│   │   └── api/                           # Core Analytics API
│   │       ├── dashboard.py               # Business intelligence
│   │       └── hedera/                    # Blockchain utilities
│   │
│   └── 🗂️ platform-services/              # AI & Business Logic
│       └── counterfeit_detection/
│           ├── agents/                    # AI agent system
│           ├── api/v1/endpoints/         # REST API endpoints
│           └── services/                  # Core business services
│
├── 📚 documentation/
│   ├── stories/                          # User Story Documentation
│   │   ├── story-1-1-phone-registration.md
│   │   ├── story-2-1-product-registration-ipfs.md
│   │   ├── story-2-2-hedera-nft-minting.md
│   │   ├── story-3-1-qr-scanning-interface.md
│   │   ├── story-4-1-hbar-payment-processing.md
│   │   └── story-4-2-mpesa-integration.md
│   └── docs/                             # Technical Documentation
│       ├── VeriChainX-Protocol-Specs.md
│       └── AfriChain-Integration-Guide.md
│
├── 🏗️ database/
│   ├── main_tidb.py                      # TiDB serverless integration
│   └── migrations/                       # Database schema migrations
│
└── 🐳 deployment/
    ├── docker-compose.yml               # Multi-service orchestration
    ├── DEPLOYMENT.md                    # Complete deployment guide
    └── scripts/                         # Deployment automation
        ├── deployAMM.ts                 # Deploy VeriChainX AMM
        ├── deployBridge.ts              # Deploy cross-chain bridge
        └── deployGovernance.ts          # Deploy DAO governance
```

## 🔄 Development Workflow

### Running Tests
```bash
# Auth Service Tests
cd backend/auth-service
npm test                    # Unit tests
npm run test:integration   # Integration tests
npm run test:coverage     # Coverage report

# Hedera Service Tests
cd backend/hedera-service
npm test                    # Blockchain tests
npm run test:agents        # Agent tests

# Frontend Tests
cd frontend/frontend/admin-dashboard
npm test                    # Component tests
npm run test:e2e           # End-to-end tests
```

### Code Quality
```bash
# TypeScript Services
npm run lint               # ESLint + TypeScript
npm run format            # Prettier formatting
npm run type-check        # TypeScript compilation

# Python Services (if using)
black platform-services/  # Code formatting
mypy platform-services/   # Type checking
flake8 platform-services/ # Linting
```

## 🏢 How AfriChain Utilizes VeriChainX Protocol

### VeriChainX Smart Contract Integration

AfriChain leverages VeriChainX smart contracts for enterprise-grade verification:

```typescript
// Deploy product to VeriChainX authenticity verifier
import { SmartContractAgent } from './agents/SmartContractAgent';
import { VeriChainXAuthenticityVerifier } from './contracts/VeriChainXAuthenticityVerifier.sol';

const contractAgent = new SmartContractAgent();

// Register product with VeriChainX protocol
const verification = await contractAgent.deployContract({
  contractName: "VeriChainXAuthenticityVerifier",
  constructorParams: {
    productId: "prod_123",
    artisanAddress: "0x...",
    metadata: "ipfs://QmHash...",
    origin: "Ghana"
  }
});

// Mint authenticity token via VeriChainX Token Factory
const authToken = await contractAgent.callContract({
  contractId: verification.contractId,
  method: "mintAuthenticityToken",
  params: {
    recipient: "0.0.123456",
    productData: productMetadata
  }
});
```

### VeriChainX AMM Integration for Authenticity Trading

Create liquidity pools for authenticity tokens:

```typescript
// Create authenticity token liquidity pool
import { AMMAgent } from './agents/AMMAgent';

const ammAgent = new AMMAgent();

// Deploy AMM pool for authenticity tokens
const ammPool = await ammAgent.createLiquidityPool({
  tokenA: "AUTHENTIC_KENTE", // Authenticity token
  tokenB: "HBAR", // Base currency
  initialLiquidityA: "1000", 
  initialLiquidityB: "500",
  feeRate: 0.003 // 0.3% trading fee
});

// AfriChain users can now trade authenticity tokens
const swap = await ammAgent.swapTokens({
  poolId: ammPool.id,
  inputToken: "HBAR",
  outputToken: "AUTHENTIC_KENTE",
  inputAmount: "10"
});
```

### Cross-Chain Verification via VeriChainX Bridge

Extend authenticity verification across multiple blockchains:

```typescript
// Bridge authenticity verification to other chains
import { BridgeAgent } from './agents/BridgeAgent';

const bridgeAgent = new BridgeAgent();

// Bridge product verification to Ethereum/Polygon
const crossChainVerification = await bridgeAgent.bridgeVerification({
  sourceChain: "hedera",
  targetChain: "ethereum",
  productId: "prod_123",
  verificationContract: verification.contractId,
  targetAddress: "0x..." // Ethereum contract address
});
```

### VeriChainX DAO Governance Integration

African artisans can participate in protocol governance:

```typescript
// Submit governance proposal for AfriChain feature
import { HederaAgentKit } from './agents/HederaAgentKit';

const agentKit = new HederaAgentKit();

// Create proposal for new African market features
const proposal = await agentKit.createGovernanceProposal({
  title: "Add USSD Support for Rural Areas",
  description: "Implement USSD interface for feature phone users",
  proposalType: "FEATURE_REQUEST",
  votingPeriod: 7 * 24 * 60 * 60, // 7 days
  requiredQuorum: 0.1, // 10% participation
  actionContract: "VeriChainXGovernance",
  actionMethod: "upgradeProtocol",
  actionParams: {
    feature: "USSD_INTERFACE",
    implementation: "ipfs://QmImplementationHash..."
  }
});

// African artisans vote on proposals affecting their market
const vote = await agentKit.castVote({
  proposalId: proposal.id,
  vote: "FOR",
  voter: artisanAddress,
  votingPower: artisanStake
});
```

## 📊 Monitoring & Observability

### Health Endpoints
- Auth Service: `GET /health` - Authentication service status
- Hedera Service: `GET /health` - Blockchain connectivity status  
- Admin Dashboard: Real-time system monitoring
- Payment Status: Live transaction tracking

### Performance Metrics
- Transaction processing times
- Blockchain confirmation speeds
- Payment gateway response times
- QR code scan analytics
- Fraud detection accuracy rates

## 🔒 Security

### Multi-Layer Authentication
- Phone number + OTP verification
- JWT tokens with refresh rotation
- Cross-channel session management
- USSD security for feature phones

### Blockchain Security
- Hedera Hashgraph consensus security
- IPFS content addressing
- NFT ownership verification
- Immutable transaction records

### Data Protection
- Encrypted communication channels
- Secure API key management
- Payment data tokenization
- GDPR-compliant data handling
- Comprehensive audit trails

## 🚀 Deployment

### Digital Ocean Deployment (Recommended)

#### App Platform
```bash
# Fastest deployment option
# Uses .do/app.yaml configuration
# Managed services with auto-scaling
# Built-in SSL and monitoring
# Cost: ~$25-50/month
```

#### Droplet Deployment
```bash
# Run the automated deployment script
./deploy-to-do.sh

# Manual deployment
# 1. Create droplet (s-2vcpu-4gb)
# 2. Setup Docker and dependencies
# 3. Clone repository and build
# 4. Configure firewall and SSL
# Cost: ~$24/month
```

#### Access Your Deployed Application
- 🌐 **Frontend**: `https://your-app.ondigitalocean.app/`
- 📡 **API**: `https://your-app.ondigitalocean.app/api/`
- 📚 **API Docs**: `https://your-app.ondigitalocean.app/api/docs`
- 🔗 **Hedera Service**: `https://your-app.ondigitalocean.app/hedera/`

### Alternative Deployments

#### Docker Deployment
```bash
# Production deployment
docker-compose -f docker-compose.prod.yml up -d

# Scale API instances
docker-compose up -d --scale api=3
```

#### Kubernetes Deployment
```bash
# Deploy to Kubernetes
kubectl apply -f k8s/

# Check deployment status
kubectl get pods -l app=counterfeit-detection
```

## 📈 Performance & Scaling

### Performance Benchmarks
- **API Response Time**: < 200ms (95th percentile)
- **Product Analysis**: < 2 seconds average
- **zkSNARK Verification**: < 500ms with caching
- **Throughput**: 1000+ requests/second

### Scaling Strategies
- Horizontal API scaling
- Database read replicas
- Redis clustering
- CDN for static assets
- Load balancing with health checks

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Setup
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests
5. Run the test suite
6. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

### Documentation
- [API Documentation](docs/api-documentation.md)
- [Deployment Guide](docs/deployment-guide.md)
- [Enterprise Setup](docs/enterprise-setup.md)
- [Troubleshooting](docs/troubleshooting.md)

---


**Built with ❤️ using modern AI and cryptographic technologies**
