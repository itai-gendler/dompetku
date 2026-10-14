---
kind: primary
routes:
  r: Web
steps:
- text: The Owner reads the Account report for a month
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Balance, Currency]}
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Date, Description]}
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: reconciliation, effect: reads, facts: [As-of date, Statement balance, App balance, Difference]}
  contexts:
    r:
      place: web::app::account-detail
---

# See an account's report

## Trigger

The owner opens an account.

## Outcome

The account's 12-month balance, the month's flows, spending per category and the last reconciliation are shown.
