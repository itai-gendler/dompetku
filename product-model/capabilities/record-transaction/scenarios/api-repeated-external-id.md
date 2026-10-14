---
kind: edge
routes:
  r: API
steps:
- text: The n8n automation posts a Transaction with a key it sent before
  kind: actor
  actor: n8n-automation
  entities:
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: automation-api
- text: A Transaction with that key exists
  kind: condition
  actor: n8n-automation
  entities:
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: automation-api
- text: The Product answers that it was recorded before
  kind: product
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
---

# n8n repeats a transaction

## Trigger

An n8n workflow posts a transaction with an idempotency key that was already used.

## Outcome

The existing transaction is returned and nothing new is saved.
