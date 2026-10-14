---
availability:
- place: automation-api
references:
- kind: code
  role: implementation
  target: src/routes/api/public/n8n/reminders-send-email.ts
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#sendReminderEmail
---

# Send reminder email

Email the reminders through the configured email service when an n8n schedule asks. By default nothing is sent when there is nothing to remind.
