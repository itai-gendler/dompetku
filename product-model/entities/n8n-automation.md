---
kind: system
acts: external
references:
- kind: code
  role: implementation
  target: src/lib/api-key.server.ts#checkApiKey
- kind: doc
  role: intent
  target: docs/N8N.md
  title: n8n guide
---

# n8n automation

The owner's own n8n workflows calling the automation API with the n8n API key: they forward Telegram updates, fetch reminders and reports on a schedule and save backups.
