---
kind: alternative
routes:
  r: API
steps:
- text: The n8n automation asks for a backup
  kind: actor
  actor: n8n-automation
  entities: []
  contexts:
    r:
      place: automation-api
- text: The Product returns the backup of every Account, Transaction and the rest of the data
  kind: product
  actor: n8n-automation
  entities:
  - {entity: account, effect: reads, facts: []}
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: automation-api
---

# n8n fetches a backup

## Trigger

An n8n weekly schedule asks for a backup to store in Google Drive or email.

## Outcome

The same JSON comes back with a filename.
