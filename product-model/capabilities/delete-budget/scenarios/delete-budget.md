---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Budget and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: budget, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::budgets
- text: The Product removes the Budget
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: removes}
  contexts:
    r:
      place: web::app::budgets
---

# Delete a budget

## Trigger

The owner deletes a budget and confirms.

## Outcome

The category no longer has a limit.
