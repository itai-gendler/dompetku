---
kind: validation
routes:
  r: Web
steps:
- text: The Family member holds only View on the account
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Family member reads the Pocket list of the account
  kind: actor
  actor: family-member
  entities:
  - {entity: pocket, effect: reads, facts: [Name, Remaining]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product offers no way to change or delete the pockets and refuses a request to
  kind: product
  actor: family-member
  entities:
  - {entity: pocket, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
---

# A member with View cannot delete a pocket

## Trigger

A family member who may only view the account tries to delete a pocket.

## Outcome

The pocket stays and the member is refused.
