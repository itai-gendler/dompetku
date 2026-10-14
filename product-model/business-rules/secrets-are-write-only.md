---
appliesTo:
- {type: capability, id: change-integration-settings}
- {type: capability, id: download-backup}
- {type: entity, id: integration-settings}
references:
- kind: code
  role: implementation
  target: src/lib/integrations.server.ts#readIntegrations
---

# Integration secrets are never shown again

The bot token, AI key, email key and n8n API key are stored encrypted and shown only as a masked hint; they are left out of backups.
