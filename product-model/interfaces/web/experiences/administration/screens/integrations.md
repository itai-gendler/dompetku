---
entities:
- {entity: integration-settings, shows: [Allowed chat IDs, Chat AI mode, Daily AI limit per chat, AI endpoint, Receipt model, Chat model, Email sender, Email recipient], collects: [Telegram bot token, Allowed chat IDs, Chat AI mode, Daily AI limit per chat, AI endpoint, AI key, Receipt model, Chat model, Resend key, Email sender, Email recipient, n8n API key]}
references:
- kind: code
  role: implementation
  target: src/components/integrations-card.tsx
---

# Integrations

The Telegram, AI, email and n8n settings, each showing whether it comes from here, from the deployment or from the default; secrets only as a masked hint.
