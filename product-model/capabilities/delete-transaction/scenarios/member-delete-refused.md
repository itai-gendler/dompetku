---
kind: validation
routes:
  r: Web
steps:
- text: The Family member asks to delete a Transaction on a view-only account
  kind: actor
  actor: family-member
  entities:
  - {entity: transaction, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Product refuses
  kind: product
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
---

# A member without Manage cannot delete

## Trigger

A family member who may only view an account tries to delete one of its transactions.

## Outcome

The transaction stays and the member is refused.
