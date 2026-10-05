# 04 · Run your agent 24/7 on a VPS (Ubuntu checklist)

A small VPS (2 vCPU, 4 GB RAM) is enough for OpenClaw or Hermes with a hosted model. Local models need much more RAM or a GPU.

## 1. Create a non-root user

```bash
adduser agent
usermod -aG sudo agent
su - agent
```

## 2. Update the server

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y curl git
```

## 3. Turn on the firewall

```bash
sudo ufw allow OpenSSH
sudo ufw enable
sudo ufw status
```

Only open extra ports if you really need them. Prefer an SSH tunnel to reach a web control panel instead of exposing it to the internet.

## 4. Install the agent

Follow [01 · OpenClaw 2.0](01-openclaw-2.0-install.md) or [03 · Hermes Agent](03-hermes-agent-install.md).

## 5. Keep it running after you log out

- **OpenClaw:** `openclaw onboard --install-daemon` installs the background service.
- **Hermes:** run the gateway as a service or inside `tmux` so it survives disconnects:

```bash
sudo apt install -y tmux
tmux new -s hermes
hermes gateway start
# press Ctrl+B then D to leave it running
```

## 6. Protect your keys

- Never paste API keys into chat messages or commit them to Git
- Use the agent's own config commands or environment variables
- Rotate keys if anyone else had access during setup

## 7. Health check

```bash
openclaw doctor          # OpenClaw
hermes config get        # Hermes
```
