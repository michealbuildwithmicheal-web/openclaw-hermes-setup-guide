# 01 · Install OpenClaw 2.0

OpenClaw 2.0 (v2026.8.1) is a self-hosted personal AI agent. It runs on your own machine and connects to your chat apps.

> Commands below follow the official install docs: https://docs.openclaw.ai/install

## Requirements

- macOS, Linux (Ubuntu 22.04+ recommended) or Windows
- **Node 24.16+ or 26.1+** (the installer adds Node automatically on macOS and Linux if it's missing)
- An AI model: a ChatGPT or Claude subscription, an API key, or a local model (e.g. Ollama)

## Option A · Installer script (recommended)

macOS / Linux / WSL2:

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

Windows PowerShell:

```powershell
iwr -useb https://openclaw.ai/install.ps1 | iex
```

## Option B · npm

```bash
npm install -g openclaw@latest --allow-scripts=openclaw
```

## Run onboarding

Onboarding connects your model and installs the background service (daemon) so the gateway keeps running after you log out:

```bash
openclaw onboard --install-daemon
```

OpenClaw 2.0 auto-detects available models (subscriptions, API keys and local models) during setup.

## Check that it works

```bash
openclaw gateway status   # is the gateway running?
openclaw doctor           # full health check
```

Then open the browser control panel (new in 2.0) to manage chats, settings and tasks.

## Keep it updated

```bash
openclaw update
```

➡️ Next: [Upgrade from OpenClaw 1.x](02-openclaw-upgrade-1x-to-2.0.md)
