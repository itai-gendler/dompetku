---
kind: validation
routes:
  r: Web
steps:
- text: The Owner enters a name another Pocket of the account already has
  kind: actor
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: [Name]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product refuses the new pocket
  kind: product
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
---

# The pocket name is taken

## Trigger

The name is already used by another pocket of the account.

## Outcome

No pocket is added and the person is told the name is used in this account.
