---
kind: alternative
routes:
  r: Web
steps:
- text: The Family member exports the month
  kind: actor
  actor: family-member
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Product builds the CSV of each visible Transaction
  kind: product
  actor: family-member
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Date, Description]}
  - {entity: wallet-access, effect: reads, facts: [Level]}
  contexts:
    r:
      place: web::app::transactions
---

# A member exports transactions

## Trigger

A family member exports a month.

## Outcome

The CSV holds only their visible transactions, other accounts masked as Other wallet.
