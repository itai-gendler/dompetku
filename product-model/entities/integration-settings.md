---
domain: settings
singleton: true
references:
- kind: code
  role: implementation
  target: src/lib/integrations.ts#INTEGRATIONS
- kind: code
  role: implementation
  target: src/lib/integrations.server.ts#saveIntegration
---

# Integration settings

The Telegram, AI, email and n8n settings, kept once. A value saved here wins over the deployment's configuration; secrets are stored encrypted and only a masked hint is ever shown again.

## Information kept

- **Telegram bot token** — secret; enables the Telegram direct mode
- **Allowed chat IDs** — the chats the bot answers; empty refuses every chat
- **Chat AI mode** — auto (AI only when quick parsing fails), always or never
- **Daily AI limit per chat** — bot AI calls allowed per chat per day; 50 by default, 0 for unlimited
- **AI endpoint** — an OpenAI-compatible chat completions address
- **AI key** — secret
- **Receipt model** — the vision model used for receipts
- **Chat model** — an optional cheaper model for chat messages
- **Resend key** — secret; enables direct reminder email
- **Email sender** — the reminder email's sender
- **Email recipient** — the reminder email's recipient
- **n8n API key** — secret of at least 24 characters that the automation API requires
