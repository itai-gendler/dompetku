---
kind: primary
routes:
  r: Web
steps:
- text: The Product adds up this month's expenses per Category and the carry of each rollover Budget
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount in IDR, Date]}
  - {entity: budget, effect: reads, facts: [Monthly limit, Rollover]}
  - {entity: category, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::budgets
- text: The Owner reads each Budget
  kind: actor
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: [Monthly limit, Alert percent, Spent this month, Carried amount, Effective limit]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::budgets
---

# See this month's budgets

## Trigger

The owner opens Budgets.

## Outcome

Each budget shows spent against its effective limit, the carried amount when rollover is on and where the warning is.

## Edge cases

- With rollover on, a month whose carry has eaten the whole limit counts as already exhausted.
