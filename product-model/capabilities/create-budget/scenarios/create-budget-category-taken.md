---
kind: validation
routes:
  r: Web
steps:
- text: The Owner picks a Category that already has a Budget
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name]}
  - {entity: budget, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::budgets
- text: The Product refuses the second budget
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::budgets
---

# The category already has a budget

## Trigger

The owner picks a category that already has a budget.

## Outcome

No second budget is made.
