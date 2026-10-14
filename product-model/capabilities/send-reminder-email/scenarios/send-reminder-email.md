---
kind: primary
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
- text: Reminders exist and the email service, sender and recipient are configured
  kind: condition
  actor: n8n-automation
  entities:
  - {entity: integration-settings, effect: reads, facts: [Resend key, Email sender, Email recipient]}
  contexts:
    r:
      place: automation-api
- text: The Product sends the email listing each bill
  kind: product
  actor: n8n-automation
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date]}
  - {entity: subscription, effect: reads, facts: [Name, Amount, Next due date]}
  contexts:
    r:
      place: automation-api
---

# Email the reminders

## Trigger

An n8n schedule asks the app to send the reminder email.

## Outcome

An email with every reminder of the window goes to the configured recipient, or to the address asked for.
