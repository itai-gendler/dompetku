---
kind: alternative
routes:
  r: API
steps:
- text: The n8n automation asks for the reminders
  kind: actor
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
- text: No number of days is given, so the reminder days from App settings apply, else 7
  kind: condition
  actor: n8n-automation
  entities:
  - {entity: app-settings, effect: reads, facts: [Reminder days]}
  contexts:
    r:
      place: automation-api
- text: The Product returns the bills and budget warnings in the window with a message to send
  kind: product
  actor: n8n-automation
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date]}
  - {entity: subscription, effect: reads, facts: [Name, Amount, Next due date]}
  - {entity: budget, effect: reads, facts: [Spent this month]}
  contexts:
    r:
      place: automation-api
---

# n8n fetches reminders

## Trigger

An n8n schedule asks for the reminders, optionally as a ready-made email.

## Outcome

The reminders come back as a list with a chat-ready message, and as subject, text and HTML when asked.
