---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member holds Wallet access to some accounts
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::accounts
- text: The Family member reads each shared Account with its balance
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: [Name, Type, Currency, Balance]}
  contexts:
    r:
      place: web::app::accounts
---

# A member browses shared accounts

## Trigger

A family member opens Accounts.

## Outcome

Only accounts with View or Manage access are listed.
