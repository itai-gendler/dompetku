---
domain: settings
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: src/lib/integrations.server.ts#saveIntegration
- kind: code
  role: implementation
  target: src/lib/integrations.ts#validateIntegration
---

# Change integration settings

The owner sets the Telegram, AI, email and n8n settings in the app instead of the deployment. A saved value wins over the deployment's; removing it falls back to the deployment's value or the default. Secrets are encrypted and shown again only as a masked hint.
