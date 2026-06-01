# 🐛 BugBusted

<div align="center">

**Privacy-First CLI Security Scanner — Powered by Local AI**

![npm](https://img.shields.io/badge/npm-i%20-g%20bugbusted-CC3534?style=for-the-badge&logo=npm&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Privacy](https://img.shields.io/badge/Data%20Egress-Zero-brightgreen?style=for-the-badge&logo=shield&logoColor=white)
![Ollama](https://img.shields.io/badge/AI-Ollama%20Local-FF6B35?style=for-the-badge&logo=llama&logoColor=white)
![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)

*Find leaked secrets. Detect misconfigurations. Stay private.*

</div>

---

## ⚡ Quick Install

```bash
npm install -g bugbusted
```

Then launch:

```bash
bugbusted
```

That's it! No complex configurations. No API keys. No cloud setup required.

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

Don't have Node.js? Download the LTS version at [nodejs.org](https://nodejs.org).

---

## 🚀 Getting Started

### Step 1 — Install BugBusted

```bash
npm install -g bugbusted
```

### Step 2 — Launch

```bash
bugbusted
```

You'll see the BugBusted interactive workspace:

```
  🆓 BugBusted Free Tier
  /scan (unlimited) | /help
  Upgrade → bugbusted.dev

~ /
```

### Step 3 — Scan a File or Directory

To scan, type `/scan` followed by the path to a file or folder:

```bash
/scan .env
```

> 💡 **Tip:** You can also type a path directly (e.g., `./config.json` or `.`) without any command to scan it instantly.

---

## 🤖 Optional — Enable AI Features

AI-powered risk explanations use [Ollama](https://ollama.com) running locally on your machine.
**Your secrets and code never leave your computer.**

### 1. Install Ollama

* **macOS**: `brew install ollama` or download the installer from [ollama.com](https://ollama.com).
* **Windows / Linux**: Download the installer from [ollama.com](https://ollama.com) and run it.

### 2. Pull the AI Model

```bash
ollama pull gemma2
```

### 3. Start Ollama

Ensure the Ollama service is running:
```bash
ollama serve
```

BugBusted auto-detects Ollama on startup. If Ollama is offline, BugBusted gracefully uses a fast, rule-based local fallback — so it still works great offline.

---

## 💬 Commands

### 🆓 Free Tier — No License Needed

| Command | What it does |
|---------|-------------|
| `/scan [path]` | Scan files or folders for secrets, misconfigurations, and gitignore gaps (unlimited) |
| `/help` | Show all available commands |
| `/pwd` | Show the current working directory |
| `/cd <path>` | Change directory |
| `/back` | Navigate up to the parent directory |
| `/clear` | Clear the terminal screen |
| `/exit` | Exit BugBusted |

### 🔒 Pro Tier — Requires License Key

| Command | What it does |
|---------|-------------|
| `/explain <file>` | Local AI explains security risks and exploit potential in plain English |
| `/check [key]` | Check for consistency/mismatched values of a key across all config files |
| `/search <value>` | Globally search for any key or value across all configurations |
| `/export <file>` | Export scan report as a `.json` or `.html` file |
| `/diff <f1> <f2>` | Compare two configuration files side-by-side |
| `/hook [ins\|rem]` | Install or remove automated Git pre-commit security gates |
| `/templates` | Browse and load secure, production-ready config templates |
| `/ignore <pattern>` | Add suppression rules to `.bugbustedignore` |
| `/init` | Generate a clean `.env.example` template from your `.env` |
| **`/model [name]`** | View or switch active local Ollama models |

---

## 🔑 Activate Pro License

### Step 1 — Get your Machine ID

```bash
bugbusted --machine-id
# Output: Your Machine ID: a1b2c3d4e5f6g7h8
```

### Step 2 — Obtain a Key

Go to [bugbusted.dev](https://bugbusted.dev) and submit your Machine ID. Alternatively, email your Machine ID to **bhagyeshpatil2004@gmail.com** or **bhagyeshpatil88@gmail.com**.

### Step 3 — Activate

```bash
bugbusted --activate BB-yourkey.signature
```

You'll see:
```
✅ BugBusted Pro activated!
   Licensed to : your@email.com
   Valid until : 1 June 2027
   Machine ID  : a1b2c3d4e5f6g7h8
   All commands unlocked 🐛
```

Check your license status anytime by running:
```bash
bugbusted --license
```

> [!WARNING]
> **Machine & OS Binding:** Licenses are bound to your machine hardware configuration and OS. A key generated for Windows will not work on macOS or Linux. Contact support if you need to transfer your license.

---

## 📁 Supported File Formats

| Category | Formats |
|----------|---------|
| **Environment** | `.env` `.env.local` `.env.production` `.env.example` |
| **Infrastructure** | `Dockerfile` `docker-compose.yml` `kubernetes.yaml` `nginx.conf` |
| **Data** | `.yaml` `.json` `.toml` `.ini` |

---

## 🔍 What BugBusted Detects

| Issue | Examples |
|-------|---------|
| **Leaked API Keys** | AWS, Stripe, GitHub, Google, OpenAI, Slack |
| **Hardcoded Passwords** | Plain text credentials in configuration blocks |
| **High Entropy Strings** | Random strings likely to be database credentials or secret tokens |
| **Misconfigurations** | Invalid formats, duplicate keys, type errors, invalid URLs |
| **Gitignore Gaps** | Flagging unignored files that contain secrets |
| **Cross-file Conflicts** | Mismatched values for the same key across config layers |

---

## 🆚 How BugBusted Compares

| Feature | Gitleaks | TruffleHog | Snyk | **BugBusted** |
|---------|:--------:|:----------:|:----:|:-------------:|
| Multi-format parsing | ❌ | ❌ | Partial | ✅ (10 formats) |
| Local AI explanation | ❌ | ❌ | ❌ | ✅ |
| Interactive REPL | ❌ | ❌ | ❌ | ✅ (17 commands) |
| Gitignore gap check | ❌ | ❌ | ❌ | ✅ |
| Git pre-commit hook | ✅ | ❌ | ✅ | ✅ |
| **Zero data egress** | ✅ | ✅ | ❌ | ✅ |
| **Works 100% offline** | ✅ | ✅ | ❌ | ✅ |

---

## ❓ Troubleshooting

**"command not found: bugbusted"**
```bash
# Try running with npx:
npx bugbusted

# Or reinstall globally:
npm install -g bugbusted
```

**"Ollama not detected"**
```bash
# Start Ollama first:
ollama serve
# Note: BugBusted will still function using rule-based local explanations if Ollama is offline.
```

**"License key invalid"**
```bash
# Ensure your active machine ID matches:
bugbusted --machine-id
# Send it to: bhagyeshpatil2004@gmail.com
```

---

## 🔒 Privacy Guarantee

- ✅ All scanning and format checks run locally on your CPU.
- ✅ AI explanations run locally via Ollama (`localhost:11434` only).
- ✅ Zero telemetry and zero data egress to external servers.
- ✅ Works 100% offline.

---

## 📄 License

```
BugBusted Proprietary License
Copyright (c) 2026 Bhagyesh Patil. All rights reserved.

The BugBusted software CLI package is proprietary. You may:
  ✅ Install and use BugBusted via npm
  ✅ Use the free tier at no cost
  ✅ Purchase a Pro license for full access

You may NOT:
  ❌ Copy, modify or distribute the software
  ❌ Reverse engineer or decompile BugBusted
  ❌ Resell or sublicense BugBusted
  ❌ Share license keys with others

For licensing inquiries contact: bhagyeshpatil2004@gmail.com
```

---

<div align="center">

Built with 🐛 by [Bhagyesh Patil](https://linkedin.com/in/bhagyeshpatil2004)

</div>
