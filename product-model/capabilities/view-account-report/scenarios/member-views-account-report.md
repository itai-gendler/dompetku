---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member holds Wallet access to the account
  kind: condition
  actor: family-member
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Family member reads the Account report
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: [Name, Balance]}
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Date]}
  contexts:
    r:
      place: web::app::account-detail
---

# A member sees a shared account's report

## Trigger

A family member opens an account shared with them.

## Outcome

The same report is shown; transfers to accounts they cannot see read Other wallet.
