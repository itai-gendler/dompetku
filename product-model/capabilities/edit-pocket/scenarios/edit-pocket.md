---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Pocket and saves
  kind: actor
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: [Name, Allocated amount, Low-balance threshold, Period, Archived, Remaining]}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: pocket, effect: changes, facts: [Name, Allocated amount, Low-balance threshold, Period, Archived]}
  contexts:
    r:
      place: web::app::account-detail
---

# Edit a pocket

## Trigger

The owner edits a pocket.

## Outcome

The pocket's remaining amount follows the new allocation.
