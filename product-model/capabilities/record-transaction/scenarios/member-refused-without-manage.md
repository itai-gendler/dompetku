---
kind: validation
routes:
  r: Web
steps:
- text: The Family member submits a transaction on an Account without Manage
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
- text: The Product refuses the transaction
  kind: product
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: transaction, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::transactions
---

# A member without Manage is refused

## Trigger

A family member tries to record on an account they may only view, or a transfer to an account they do not manage.

## Outcome

Nothing is saved and the member is refused.
