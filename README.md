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
| CAPTCHA | Type the characters shown on screen |

---

## 📋 Features

### Login Page
- Text-based CAPTCHA (6-character alphanumeric, randomised each attempt)
- F5 Bot Defense demo badge
- Error handling with CAPTCHA refresh on failed login

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
