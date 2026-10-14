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
      place: web::app::transactions
- text: The Family member reads the visible Transaction list
  kind: actor
  actor: family-member
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Date, Description]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::transactions
---

# A member browses transactions

## Trigger

A family member opens Transactions.

## Outcome

Only transactions touching shared accounts are listed; the other side of a transfer to an unshared account reads Other wallet.
