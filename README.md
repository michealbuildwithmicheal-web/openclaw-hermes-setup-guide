# ⚙️ OpenClaw 2.0 & Hermes Agent Setup Guide

![OpenClaw 2.0](https://img.shields.io/badge/OpenClaw-2.0-E5383B?style=for-the-badge)
![Hermes Agent](https://img.shields.io/badge/Hermes_Agent-v0.21-6E40C9?style=for-the-badge)
![VPS](https://img.shields.io/badge/VPS%20%C2%B7%20Mac%20Mini%20%C2%B7%20PC-ready-222?style=for-the-badge)
![License: MIT](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

A clear, step-by-step guide to **install OpenClaw 2.0 and Hermes Agent**, **upgrade from OpenClaw 1.x without breaking anything**, and run your AI agent **24/7 on a VPS**.

Commands follow the official docs and were current as of **October 2026**.

## 📚 Guides

| # | Guide | What you'll do |
|---|---|---|
| 01 | [Install OpenClaw 2.0](guides/01-openclaw-2.0-install.md) | Installer or npm, onboarding, gateway and doctor checks |
| 02 | [Upgrade 1.x → 2.0](guides/02-openclaw-upgrade-1x-to-2.0.md) | Backup, update, `doctor --fix` migrations, verification checklist, quick fixes |
| 03 | [Install Hermes Agent](guides/03-hermes-agent-install.md) | Install, model and tools setup, chat gateway, migrate from OpenClaw |
| 04 | [VPS checklist](guides/04-vps-checklist.md) | Secure Ubuntu server, firewall, keep agents running 24/7, protect API keys |

## ⚡ Quick start

**OpenClaw 2.0**

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
openclaw onboard --install-daemon
openclaw gateway status
```

**Hermes Agent**

```bash
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
source ~/.bashrc
hermes setup
```

## 🤔 OpenClaw or Hermes?

| | OpenClaw 2.0 | Hermes Agent |
|---|---|---|
| Built with | TypeScript / Node | Python |
| Best for | Personal assistant across many chat apps, team sessions | Self-improving agent with memory, skills and Bot Mode |
| New in latest version | Guided model setup, browser control panel, shared sessions | Bot Mode, bot-to-bot messaging, memory-aware cron jobs |

You can run both, and Hermes can import an OpenClaw setup with `hermes claw migrate`.

## 📖 Official docs

- OpenClaw: https://docs.openclaw.ai
- Hermes Agent: https://github.com/NousResearch/hermes-agent

## 👋 Need it done for you?

I'm **Michael Frank**. I install, upgrade and fix **OpenClaw 2.0, Hermes Agent and Grok Bot** on VPS, Mac Mini or PC, connected to Telegram, Gmail, Claude or local models.

**Message me on Fiverr** and tell me about your setup.

## 📄 License

MIT
