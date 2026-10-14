---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Account and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::accounts
- text: The Product removes the Account with its Pocket list and each Wallet access
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: removes}
  - {entity: pocket, effect: removes, with: account}
  - {entity: wallet-access, effect: removes, with: account}
  contexts:
    r:
      place: web::app::accounts
---

# Delete an account

## Trigger

The owner deletes an account and confirms.

## Outcome

The account, its pockets and every wallet access to it are gone; its transactions stay without an account.
