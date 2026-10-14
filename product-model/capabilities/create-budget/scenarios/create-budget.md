---
kind: primary
routes:
  r: Web
steps:
- text: The Owner picks an expense Category and enters the limit, warning percent and rollover
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::budgets
- text: The Product keeps the Budget
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: creates, facts: [Monthly limit, Alert percent, Rollover]}
  contexts:
    r:
      place: web::app::budgets
---

# Set a budget

## Trigger

The owner adds a budget.

## Outcome

The category's spending this month is measured against the limit.
