---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner switches the Account to archived and saves
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Archived]}
  contexts:
    r:
      place: web::app::accounts
- text: The Product keeps the Account as archived
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: changes, facts: [Archived]}
  contexts:
    r:
      place: web::app::accounts
---

# Archive an account

## Trigger

The owner switches Archive account on.

## Outcome

The account keeps its history but is marked archived and left out of balance totals.
