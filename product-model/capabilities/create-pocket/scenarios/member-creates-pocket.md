---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member holds Manage on the Account
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Family member enters the name and allocated amount
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app::account-detail
- text: The Product keeps the new Pocket
  kind: product
  actor: family-member
  entities:
  - {entity: pocket, effect: creates, facts: [Name, Allocated amount, Low-balance threshold, Period, Archived]}
  contexts:
    r:
      place: web::app::account-detail
---

# A member adds a pocket

## Trigger

A family member with Manage on the account adds a pocket.

## Outcome

The pocket exists like one the owner added.
