# NexaBank — F5 Distributed Cloud Bot Defense Demo Portal

A self-contained membership login portal built to **demonstrate F5 Distributed Cloud Bot Defense** capabilities. No server, no build tools, no dependencies — just open `index.html` in a browser.

---

## 🚀 Quick Start

```bash
git clone https://github.com/YOUR_USERNAME/f5-demo-portal.git
cd f5-demo-portal
open index.html   # macOS
# or just double-click index.html in your file explorer
```

> Or host it instantly with GitHub Pages — see [Deployment](#-deployment) below.

---

## 🔐 Demo Credentials

| Field | Value |
|-------|-------|
| Username | `john.doe` |
| Password | `password123` |
| CAPTCHA | Type the characters shown on the canvas image |

---

## 🎯 Demo Walkthrough — Step by Step

Use these steps to walk an audience through the portal during a live F5 Distributed Cloud Bot Defense presentation.

---

### Step 1 — Show the Login Page (CAPTCHA & Bot Protection)

1. Open `index.html` in a browser. The **NexaBank login page** appears.
2. Point out the **"⚠ F5 BOT DEFENSE DEMO"** badge in the top-right corner of the card.
3. Draw attention to the **canvas-rendered Text CAPTCHA** — explain that this is a common protection mechanism on real portals.
4. Explain that **bots routinely bypass standard CAPTCHAs** using:
   - Automated CAPTCHA-solving services
   - Headless browsers (Puppeteer, Playwright, Selenium)
   - OCR-based solvers
5. Demonstrate a **failed login** by entering wrong credentials or an incorrect CAPTCHA — the error banner appears and the CAPTCHA refreshes automatically.
6. Log in successfully using `john.doe` / `password123` + the correct CAPTCHA characters.

> **Key F5 talking point:** F5 Bot Defense analyses behavioural signals (mouse movement, keystroke dynamics, browser fingerprint) — not just whether the CAPTCHA was solved — to distinguish real users from bots.

---

### Step 2 — Dashboard (Transaction-Level Bot Signals)

1. After login, the **Dashboard** loads with account stats and recent transactions.
2. Scroll to the **Recent Transactions** table.
3. Point out the row: *"Suspicious Login Blocked"* with a **Bot Blocked** badge — this illustrates that F5 is already acting at the transaction level.
4. Highlight the stat card: **"7 Bot Challenges Issued"** — showing the platform is actively challenged.

> **Key F5 talking point:** F5 Bot Defense can inject telemetry signals into every page, not just the login endpoint, giving continuous session-level protection.

---

### Step 3 — Personal Information (PII Scraping Risk)

1. Click **Personal Info** in the sidebar.
2. Walk through the sensitive data fields highlighted in **gold**:
   - Full Name, NRIC/ID Number, Date of Birth
   - Phone Number, Email Address, Residential Address
   - Gender, Membership Tier, Hobbies & Interests
3. Explain that **PII scraping bots** target pages like this to harvest data at scale for:
   - Identity fraud
   - Targeted phishing campaigns
   - Selling data on dark web marketplaces

> **Key F5 talking point:** Without bot protection, a bot can log in with stolen credentials and scrape an entire member database in minutes. F5 detects abnormal access patterns and blocks automated PII harvesting.

---

### Step 4 — Payment Methods (Carding & Card Enumeration)

1. Click **Payment Methods** in the sidebar.
2. Show the **visual credit card components** (VISA, Mastercard, Amex).
3. Point to the stored card details table — last 4 digits, expiry dates, billing addresses.
4. Explain **carding attacks**: bots use stolen card numbers to make small test transactions to verify validity before selling or using them at scale.
5. Also explain **card enumeration**: bots systematically probe checkout flows to determine which card numbers are live.

> **Key F5 talking point:** F5 Bot Defense protects payment endpoints (`/api/payment`, `/checkout`) by flagging non-human interaction patterns such as rapid sequential card submissions.

---

### Step 5 — E-Wallets (Automated Fraud Transfers)

1. Click **E-Wallets** in the sidebar.
2. Show the four linked wallet accounts (GoPay, PayNow, GrabPay, Alipay) with live balances and account IDs.
3. Scroll to the **Wallet Transactions** table.
4. Point out the row: *"Auto Top-Up (Bot?)"* with a **Blocked** badge — a $500 automated transfer that was intercepted.
5. Explain that attackers use bots to **drain e-wallets** by:
   - Triggering automatic top-ups from linked cards
   - Initiating rapid peer-to-peer transfers to mule accounts

> **Key F5 talking point:** F5 can protect e-wallet top-up and transfer endpoints, detecting bot-driven fund movement that happens faster than any human could act.

---

### Step 6 — Order History (Scalping & Inventory Abuse)

1. Click **Order History** in the sidebar.
2. Walk through the legitimate orders (electronics, fashion, books).
3. Highlight the flagged row: *"3× Bulk Orders (Bot?)"* for $2,400 — currently in **Fraud Review**.
4. Explain **scalping bots**: automated buyers that purchase limited-stock items in bulk to resell at a premium (e.g., gaming consoles, sneakers, event tickets).
5. Also explain **inventory hoarding**: bots add items to cart to deplete stock without completing purchase, blocking real customers.

> **Key F5 talking point:** F5 Bot Defense protects `/shop/cart/add` and checkout flows, using ML models trained on billions of transactions to flag non-human purchase velocity.

---

### Step 7 — Online Shop (Real-Time Bot-Protected Checkout)

1. Click **Online Shop** in the sidebar.
2. Show the product grid — highlight high-demand items like PS5 and iPhone that are common scalping targets.
3. Point to the **alert banner** at the top: *"Checkout & Add-to-Cart are monitored by F5 Bot Defense."*
4. Explain that every click on the shop sends telemetry signals to F5 cloud for analysis.

> **Key F5 talking point:** F5 Bot Defense is invisible to legitimate users but continuously scoring every interaction. A bot clicking "Add to Cart" 500 times per minute looks nothing like a human — and gets blocked in real time.

---

### Step 8 — Bot Defense Log (Attack Telemetry)

1. Click **Bot Defense Log** in the sidebar — this is the centrepiece of the F5 demo.
2. Walk through the **Bot Defense Summary** panel:
   - **1,240** total login attempts in 24 hours
   - **1,198** blocked as bots (96.6% bot traffic)
   - Only **42** legitimate users
   - **3** active credential stuffing campaigns
   - **887** CAPTCHA bypass attempts
3. Walk through the **Attack Event Log** table row by row:

   | Row | What to explain |
   |-----|----------------|
   | Credential Stuffing | Bots using leaked username/password lists against `/api/login` |
   | CAPTCHA Bypass | Automated solver detected on the login page |
   | Account Enumeration | Bot probing `/api/check-user` to discover valid usernames |
   | Headless Browser | Non-human browser fingerprint detected accessing the member profile |
   | Cart Stuffing | Bot adding items to cart via `/shop/cart/add` at inhuman speed |
   | PII Scraping | Bot harvesting member profile data at scale |
   | Legitimate User | Real human — allowed through, shown for contrast |

4. Scroll down to the **"What F5 Bot Defense Protects"** cards — use these as a visual summary of all six protection categories.

> **Key F5 talking point:** F5 Distributed Cloud Bot Defense uses a continuously updated, AI-driven signal library. Unlike rule-based WAFs, it doesn't need to know the attack pattern in advance — it detects anomalous behaviour and adapts in real time.

---

### Step 9 — Wrap-Up Talking Points

Summarise the demo with these key messages:

- **96%+ of login traffic to this portal was bots** — typical of real-world financial and e-commerce sites
- **CAPTCHA alone is not enough** — bots routinely solve or bypass them
- **F5 protects every layer**: login, PII access, payments, wallets, and checkout
- **Zero friction for real users** — legitimate members never see a challenge
- **Real-time, cloud-scale** — signals are analysed globally across all F5-protected properties

---

## 📋 Features Summary

### Login Page
- Canvas-rendered Text CAPTCHA (6-character alphanumeric, randomised each attempt)
- CAPTCHA auto-refreshes on failed login
- F5 Bot Defense demo badge

### Member Portal (6 sections)

| Section | Sensitive Data Demonstrated |
|---|---|
| **Dashboard** | Account balance, recent transactions, bot-blocked entries |
| **Personal Info** | Full name, NRIC/ID, DOB, phone, address, gender, hobbies |
| **Payment Methods** | Credit card visuals (VISA, Mastercard, Amex), card numbers, expiry |
| **E-Wallets** | GoPay, PayNow, GrabPay, Alipay — balances & account IDs |
| **Order History** | Purchase history with a bot-flagged fraud review order |
| **Bot Defense Log** | Live attack telemetry — attack types, IPs, endpoints, actions |

---

## 🛡 F5 Bot Defense Scenarios Illustrated

- **Credential Stuffing** — Mass automated login attempts against `/api/login`
- **CAPTCHA Bypass** — Headless browser and automated solver detection
- **Account Takeover (ATO)** — Blocked sessions attempting to access PII
- **PII Scraping** — Bots harvesting member profile data
- **Cart Stuffing / Scalping** — Automated add-to-cart on the shop
- **Carding Attacks** — Automated card validation attempts
- **Real-time Telemetry** — Signal-based detection feeding F5 cloud intelligence

---

## 📁 Project Structure

```
f5-demo-portal/
├── index.html      # Complete single-file demo portal
└── README.md       # This file
```

---

## 🌐 Deployment

### GitHub Pages (recommended for live demos)
1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your demo will be live at `https://YOUR_USERNAME.github.io/f5-demo-portal/`

### Local HTTP Server
```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

---

## ⚠️ Disclaimer

This portal is a **demonstration tool only**. All member data, card numbers, wallet IDs, and attack logs are entirely fictitious. This is not a real banking application. Intended for F5 sales, pre-sales, and technical demonstration purposes.

---

## 🏷 Tags

`f5` `bot-defense` `distributed-cloud` `demo` `security` `credential-stuffing` `account-takeover` `captcha` `banking-portal`
