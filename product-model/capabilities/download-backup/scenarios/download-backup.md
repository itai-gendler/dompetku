---
kind: primary
routes:
  r: Web
steps:
- text: The Owner taps Download backup
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::backup
- text: The Product builds the backup of every Account, Transaction and the rest of the data
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: []}
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::backup
---

# Download a backup

## Trigger

The owner taps Download backup.

## Outcome

A dated JSON file with all data downloads.
