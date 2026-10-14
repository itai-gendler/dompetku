---
kind: primary
routes:
  r: Web
steps:
- text: The Product totals the month and the balances
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date]}
  - {entity: account, effect: reads, facts: [Balance, Archived]}
  contexts:
    r:
      place: web::app::dashboard
- text: The Owner reads the totals, spending per Category and each low Pocket
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date, Description]}
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: pocket, effect: reads, facts: [Name, Remaining, Low-balance threshold]}
  contexts:
    r:
      place: web::app::dashboard
---

# See the owner's dashboard

## Trigger

The owner opens the dashboard.

## Outcome

Income, expense, net, balances, net worth, six months of cash flow, spending per category, upcoming bills and low pockets are shown.

## Edge cases

- Opening the dashboard first posts due monthly fees and automatic recurring occurrences.
