---
kind: validation
routes:
  r: Web
steps:
- text: The Owner enters a transfer without a destination account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::recurring-transactions
- text: The Product refuses the schedule
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::recurring-transactions
---

# A transfer needs two different accounts

## Trigger

The owner schedules a transfer without both accounts, to the same account, or ending before it starts.

## Outcome

Nothing is saved and the owner is told what to fix.
