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
      place: web::app::dashboard
- text: The Family member reads the totals of each shared Account
  kind: actor
  actor: family-member
  entities:
  - {entity: account, effect: reads, facts: [Name, Balance]}
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date]}
  contexts:
    r:
      place: web::app::dashboard
---

# See a member's dashboard

## Trigger

A family member opens the dashboard.

## Outcome

The figures cover only the member's accounts; transfers between two of them cancel out.
