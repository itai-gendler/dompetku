---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the name, allocated amount, optional low-balance threshold and period
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Balance]}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product keeps the new Pocket in that Account
  kind: product
  actor: owner
  entities:
  - {entity: pocket, effect: creates, facts: [Name, Allocated amount, Low-balance threshold, Period, Archived]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
---

# Add a pocket

## Trigger

The owner adds a pocket on an account's page.

## Outcome

The pocket is listed with its allocated amount as remaining, and the account's unallocated figure drops.
