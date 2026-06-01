# 🐛 BugBuster

<div align="center">

**Privacy-First CLI Security Scanner — Powered by Local AI**

![npm](https://img.shields.io/badge/npm-i%20-g%20bugbuster-CC3534?style=for-the-badge&logo=npm&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Privacy](https://img.shields.io/badge/Data%20Egress-Zero-brightgreen?style=for-the-badge&logo=shield&logoColor=white)
![Ollama](https://img.shields.io/badge/AI-Ollama%20Local-FF6B35?style=for-the-badge&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)

*Find leaked secrets. Fix misconfigs. Stay private.*

[Website](https://bugbuster.dev) · [Buy Pro — $29](https://bugbuster.dev/pricing) · [Report a Bug](mailto:bhagyeshpatil88@gmail.com)

</div>

---

## ⚡ Quick Install

```bash
npm install -g bugbuster
```

Then launch:

```bash
bugbuster
```

That's it. No config. No API keys. No cloud setup.

---

## 📋 Requirements

| Requirement | Version | Required? |
|-------------|---------|-----------|
| **Node.js** | 18 or higher | ✅ Yes |
| **npm** | 8 or higher | ✅ Yes |
| **Ollama** | Latest | ⚠️ Optional (for AI features) |

### Check your Node version:
```bash
node --version
# Should show v18.0.0 or higher
```

Don't have Node.js? Download at [nodejs.org](https://nodejs.org) → choose LTS version.

---

## 🚀 Getting Started

### Step 1 — Install BugBuster

```bash
npm install -g bugbuster
```

### Step 2 — Launch

```bash
bugbuster
```

You'll see the BugBuster REPL:

```
  🆓 BugBuster Free Tier
  /scan (5/day) | /audit (3/day) | /help
  Upgrade → bugbuster.dev

~ /
```

### Step 3 — Scan Your First File

```bash
/scan .env
```

BugBuster finds leaked secrets, misconfigs, and security issues instantly.

---

## 🤖 Optional — Enable AI Features

AI features use [Ollama](https://ollama.com) running locally.
**Your code never leaves your computer.**

### Install Ollama

**Mac:**
```bash
brew install ollama
```

**Windows / Linux:**
Download from [ollama.com](https://ollama.com) → follow installer

### Pull AI Model

```bash
ollama pull gemma2
```

### Start Ollama

```bash
ollama serve
```

BugBuster auto-detects Ollama on startup. If Ollama is offline, BugBuster uses a fast rule-based fallback — still works great without it.

---

## 💬 Commands

### 🆓 Free Tier — No License Needed

| Command | What it does |
|---------|-------------|
| `/scan [path]` | Scan file or folder for secrets and misconfigs (5/day) |
| `/audit [path]` | Silent health check with summary score (3/day) |
| `/help` | Show all available commands |
| `/pwd` | Show current directory |
| `/cd <path>` | Change directory |
| `/back` | Go up one directory |
| `/clear` | Clear the screen |
| `/exit` | Exit BugBuster |

### 🔒 Pro — Requires License Key

| Command | What it does |
|---------|-------------|
| `/explain <file>` | AI explains security risks in plain English |
| `/fix <file>` | AI suggests how to fix each issue |
| `/apply` | Apply AI fix directly to your file |
| `/check [key]` | Find mismatched keys across all config files |
| `/search <value>` | Search for any value across all configs |
| `/export <file>` | Export scan report as JSON or HTML |
| `/diff <f1> <f2>` | Compare two config files side by side |
| `/hook ins\|rem` | Add/remove Git pre-commit security check |
| `/templates` | Browse and use secure config templates |
| `/ignore <pattern>` | Add suppression rule to .bugbusterignore |
| `/init` | Generate .env.example from your .env |

> 💡 **Tip:** Type a file path directly (e.g. `./config.yaml`) to scan it instantly without a command.

---

## 🔑 Activate Pro License

### Step 1 — Get your Machine ID

```bash
bugbuster --machine-id
# Output: Your Machine ID: a1b2c3d4e5f6g7h8
```

### Step 2 — Purchase License

Go to [bugbuster.dev/pricing](https://bugbuster.dev/pricing)
Send your Machine ID to **bhagyeshpatil88@gmail.com** after purchase.

### Step 3 — Activate

```bash
bugbuster --activate BB-yourkey
```

You'll see:
```
✅ BugBuster Pro activated!
   Licensed to: your@email.com
   Valid until: 1 June 2027
   All commands unlocked 🐛
```

### Check License Status Anytime

```bash
bugbuster --license
```

---

## 📁 Supported File Formats

| Category | Formats |
|----------|---------|
| **Environment** | `.env` `.env.local` `.env.production` `.env.example` |
| **Infrastructure** | `Dockerfile` `docker-compose.yml` `kubernetes.yaml` `nginx.conf` |
| **Data** | `.yaml` `.json` `.toml` `.ini` |

---

## 🔍 What BugBuster Detects

| Issue | Examples |
|-------|---------|
| **Leaked API Keys** | AWS, Stripe, GitHub, Google, OpenAI |
| **Hardcoded Passwords** | Plain text passwords in config files |
| **High Entropy Strings** | Random strings likely to be secrets |
| **Misconfigurations** | Wrong URLs, duplicate keys, type errors |
| **Gitignore Gaps** | Sensitive files not in .gitignore |
| **Cross-file Conflicts** | Same key, different values across files |

---

## 📊 Performance

| Metric | Result |
|--------|--------|
| Config formats supported | 10 |
| Detection precision | 93.4% |
| Detection recall | 91.2% |
| AI response time | ~9.2 seconds |
| Offline fallback | < 100ms |
| Data sent to cloud | **0 bytes** |

---

## 🆚 How BugBuster Compares

| Feature | Gitleaks | TruffleHog | Snyk | BugBuster |
|---------|:--------:|:----------:|:----:|:---------:|
| Multi-format parsing | ❌ | ❌ | Partial | ✅ |
| Local AI explanation | ❌ | ❌ | ❌ | ✅ |
| Interactive REPL | ❌ | ❌ | ❌ | ✅ |
| Fix generation + apply | ❌ | ❌ | Partial | ✅ |
| Gitignore gap check | ❌ | ❌ | ❌ | ✅ |
| Zero data egress | ✅ | ✅ | ❌ | ✅ |
| Works 100% offline | ✅ | ✅ | ❌ | ✅ |

---

## 💰 Pricing

| Plan | Price | What you get |
|------|-------|-------------|
| **Free** | $0 forever | /scan (5/day), /audit (3/day), /help |
| **Lifetime** | $29 once | All commands, 2 machines |
| **Updates** | $9/year | New commands, parsers, features |

Team plans available at [bugbuster.dev/pricing](https://bugbuster.dev/pricing)

---

## ❓ Troubleshooting

**"command not found: bugbuster"**
```bash
# Try:
npx bugbuster

# Or reinstall:
npm install -g bugbuster
```

**"Ollama not detected"**
```bash
# Start Ollama first:
ollama serve
# BugBuster still works without it using smart fallback
```

**"License key invalid"**
```bash
# Get your machine ID:
bugbuster --machine-id
# Email it to: bhagyeshpatil88@gmail.com
# We fix same day ✅
```

**Node version too old**
```bash
node --version
# Need v18+? Download at nodejs.org
```

---

## 🔒 Privacy Guarantee

- ✅ All scanning runs on your machine
- ✅ AI runs locally via Ollama (localhost only)
- ✅ Zero data sent to any server ever
- ✅ Your secrets never leave your computer
- ✅ Works 100% offline after install

---

## 📄 License

```
BugBuster Proprietary License
Copyright (c) 2026 Bhagyesh Patil. All rights reserved.

This documentation is provided for informational purposes only.

The BugBuster software is proprietary. You may:
  ✅ Install and use BugBuster via npm
  ✅ Use the free tier at no cost
  ✅ Purchase a Pro license for full access

You may NOT:
  ❌ Copy, modify or distribute the software
  ❌ Reverse engineer or decompile BugBuster
  ❌ Resell or sublicense BugBuster
  ❌ Share license keys with others

For licensing inquiries:
bhagyeshpatil88@gmail.com
```

---

<div align="center">

Built with 🐛 by [Bhagyesh Patil](https://linkedin.com/in/bhagyeshpatil2004)

[bugbuster.dev](https://bugbuster.dev) · [bhagyeshpatil88@gmail.com](mailto:bhagyeshpatil88@gmail.com) · [LinkedIn](https://linkedin.com/in/bhagyeshpatil2004)

</div>
