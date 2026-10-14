---
type: api
actors: [n8n-automation]
references:
- kind: code
  role: implementation
  target: src/lib/api-key.server.ts#checkApiKey
- kind: doc
  role: intent
  target: n8n/README.md
  title: n8n templates
---

# Automation API

The HTTP endpoints the owner's n8n workflows call with the n8n API key: recording transactions,
reminders, reports, reminder email and backups.
