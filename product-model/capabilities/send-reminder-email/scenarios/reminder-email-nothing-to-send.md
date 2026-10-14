---
kind: edge
routes:
  r: API
steps:
- text: The n8n automation asks for the reminder email
  kind: actor
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
- text: The Product finds no reminders and sends nothing
  kind: product
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
---

# Nothing to remind

## Trigger

The window holds no reminders.

## Outcome

No email is sent and the answer says so.
