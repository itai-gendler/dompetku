---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Budget
  kind: actor
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: [Monthly limit, Alert percent, Rollover]}
  contexts:
    r:
      place: web::app::budgets
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: changes, facts: [Monthly limit, Alert percent, Rollover]}
  contexts:
    r:
      place: web::app::budgets
---

# Edit a budget

## Trigger

The owner edits a budget.

## Outcome

The new limit applies to every month of the rollover chain, since past limits are not kept.
