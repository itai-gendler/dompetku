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
- text: The email service is not configured
  kind: condition
  actor: n8n-automation
  entities:
  - {entity: integration-settings, effect: reads, facts: [Resend key, Email sender, Email recipient]}
  contexts:
    r:
      place: automation-api
- text: The Product answers that email is unavailable
  kind: product
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
---

# Email is not configured

## Trigger

The email service key, sender or recipient is missing.

## Outcome

No email is sent and the answer gives the reason as unavailable.
