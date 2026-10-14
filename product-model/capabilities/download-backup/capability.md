---
domain: settings
availability:
- place: web::administration
- place: automation-api
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#exportBackup
- kind: code
  role: implementation
  target: src/routes/api/public/n8n/backup.ts
---

# Download backup

Download every table as one JSON file, without password hashes or integration secrets. n8n workflows fetch the same file on a schedule.
