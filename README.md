# GhostBot + GhostPay

**GhostBot + GhostPay** is a **fully modular, multi-chain bot and payment ecosystem** supporting Solana and SUI, SPL token transfers, Jupiter API swaps, GhostPay private payments, Solana Pay QR/deep-link transactions, real-time oracles (Pyth + BirdEye), AI predictive actions, Telegram integration, dashboard widgets, and PWA/TWA mobile deployment.

This repository is structured for **production-ready deployment** and includes a fully modular SDK for external apps.

---

## **Features**

### Core Functionality
- Multi-chain support: **Solana + SUI**
- SPL token transfers & Jupiter API swaps
- Solana Pay QR / deep-link payments
- GhostPay privacy layer with **ZK-proof-based transactions**
- Real-time oracles: **Pyth + BirdEye**
- Dashboard backend widgets: balances, transactions, token stats
- Telegram bot integration with AI predictive actions
- User profiles, settings, and IDs
- Fully modular SDK for external app integration

### Frontend & Mobile
- **Dashboard React components & hooks**
- **PWA installable:** offline caching, push notifications
- **TWA Android deployment** ready

---

## **Repository Structure**

```

/ghostbot/
core/           # Main services: blockchain, swap, pay, AI, oracles, events
server/         # Express API, routes, middlewares
dashboard/      # React components & hooks
web/            # PWA & TWA mobile apps
data/           # JSON storage for users, tokens, transactions, messages
scripts/        # Deployment & AI task scripts
utils/          # Helper utilities
README.md

````

---

## **Getting Started**

### **1. Clone the repository**

```bash
git clone https://github.com/your-org/ghostbot.git
cd ghostbot
````

### **2. Install dependencies**

```bash
# Backend
cd server
npm install

# Core services
cd ../core
npm install

# Dashboard / PWA
cd ../dashboard
npm install
cd ../web/pwa
npm install
```

### **3. Configure environment variables**

Create a `.env` file in `/server`:

```
SOLANA_RPC_URL=https://api.mainnet-beta.solana.com
SUI_RPC_URL=https://fullnode.mainnet.sui.io
GHOSTPAY_API_URL=https://ghostpay.fund/api/v1
TELEGRAM_BOT_TOKEN=<your-telegram-bot-token>
PYTH_API_URL=https://pyth.network/api/price
BIRDEYE_API_URL=https://api.birdeye.so/api/v1
```

---

### **4. Running the backend**

```bash
cd server
npm run dev
```

API will be available at `http://localhost:3000/api/ghostbot`.

---

### **5. Running scripts**

* Deploy Telegram bot:

```bash
cd scripts
ts-node deployTelegramBot.ts
```

* Run AI tasks:

```bash
ts-node runAITasks.ts
```

---

### **6. Dashboard & PWA**

```bash
cd dashboard
npm start   # React dashboard

cd ../web/pwa
npm start   # PWA frontend
```

TWA Android app is located in `web/twa/android` for building in Android Studio.

---

## **SDK Usage**

```ts
import { GhostBotSDK } from './core/sdk/ghostbotSDK';

const solBalance = await GhostBotSDK.blockchain.getSolBalance("WALLET_ADDRESS");
const swapQuote = await GhostBotSDK.swap.getQuote("INPUT_MINT", "OUTPUT_MINT", 1000);
const paymentTx = await GhostBotSDK.pay.sendPrivatePayment("SENDER", "RECIPIENT", 10, "USDC");
```

---

## **Phase Breakdown**

### **Phase 1 — Backend + SDK**

* Blockchain services (Solana + SUI)
* Jupiter API swaps
* GhostPay & Solana Pay payments
* Pyth + BirdEye oracles
* Telegram bot + AI predictive actions
* SDK for external integration
* Scripts for deployment & AI automation

### **Phase 2 — Frontend + PWA/TWA**

* Dashboard React components & hooks
* PWA: offline caching, push notifications
* TWA: Android-ready mobile app
* Real-time integration with backend SDK

---

## **Roadmap**

* [x] Multi-chain support (Solana + SUI)
* [x] SPL token transfers + Jupiter API swaps
* [x] GhostPay private transactions + Solana Pay
* [x] Real-time oracles (Pyth + BirdEye)
* [x] Telegram bot + AI predictive actions
* [x] Dashboard backend & widgets
* [x] PWA & TWA mobile-ready frontend
* [ ] Additional blockchain support (future)
* [ ] Enhanced AI predictive actions

---

## **Contributing**

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit changes: `git commit -m "Add your feature"`
4. Push to branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## **License**

MIT License © 2026 Ghost Foundation / Ghost Protocol
