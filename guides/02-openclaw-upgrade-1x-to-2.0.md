# 02 · Upgrade OpenClaw 1.x → 2.0 (without breaking it)

Many users upgrading to OpenClaw 2.0 report broken gateways, lost automations or model login errors. Most of these come from skipping the backup or the migration step. Follow this order.

## 1. Back up first

```bash
openclaw backup sqlite
```

This creates a verifiable snapshot of your data so you can roll back if anything goes wrong.

## 2. Update

```bash
openclaw update
```

## 3. Run the migrations

```bash
openclaw doctor --fix
```

`doctor --fix` applies the 2.0 migrations and restarts the gateway. It:

- removes the retired OpenProse plugin config
- converts `codex/*` and `openai-codex/*` model references to `openai/*`
- updates provider config, stored sessions and automations

## 4. Verify everything

```bash
openclaw gateway status
openclaw doctor
```

Then check by hand:

- [ ] Send a test message on **every** connected channel (Telegram, Discord, WhatsApp, Slack...)
- [ ] Open the new browser control panel and confirm your model is connected
- [ ] Run each automation once and confirm it still triggers

## Quick fixes

| Problem after upgrading | What to try |
|---|---|
| Gateway won't start | `openclaw doctor --fix`, then `openclaw gateway status` |
| "Model not found" / auth errors | Old `codex/*` model names: re-run `openclaw doctor --fix`, then re-log in to your model provider |
| Automations missing | Check they were migrated with `openclaw doctor`; restore from your backup if needed |
| Channel stopped replying | Reconnect that channel in the control panel and send a test message |

➡️ Next: [Install Hermes Agent](03-hermes-agent-install.md)
