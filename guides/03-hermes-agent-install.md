# 03 · Install Hermes Agent

Hermes Agent by Nous Research is a self-improving AI agent with memory, skills, cron jobs and (since v0.21.0) **Bot Mode** for named bots and bot-to-bot messaging.

> Commands below follow the official repo: https://github.com/NousResearch/hermes-agent

## Install

Linux / macOS / WSL2:

```bash
curl -fsSL https://hermes-agent.nousresearch.com/install.sh | bash
source ~/.bashrc   # or ~/.zshrc
```

Windows PowerShell:

```powershell
iex (irm https://hermes-agent.nousresearch.com/install.ps1)
```

The installer sets up Python, Node.js, npm, ripgrep, FFmpeg and the Python dependencies for you.

## First-time setup

```bash
hermes setup    # full guided setup
hermes model    # choose your AI model
hermes tools    # enable the tools you want
```

Start chatting:

```bash
hermes
```

## Connect chat apps (gateway)

```bash
hermes gateway start
```

Useful commands inside any connected chat:

| Command | What it does |
|---|---|
| `/new` or `/reset` | start a fresh conversation |
| `/model provider:model` | switch AI model |
| `/personality name` | set a persona |
| `/retry`, `/undo` | redo the last turn |
| `/stop` | stop the current task |

## Settings and updates

```bash
hermes config get        # view settings
hermes config set ...    # change a setting
hermes update            # update to the latest version
```

## Coming from OpenClaw?

Hermes can import your OpenClaw setup:

```bash
hermes claw migrate
```

➡️ Next: [Run it 24/7 on a VPS](04-vps-checklist.md)
