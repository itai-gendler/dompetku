---
kind: validation
routes:
  r: Web
steps:
- text: The Owner withdraws from a Goal with nothing saved
  kind: actor
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: [Saved amount]}
  contexts:
    r:
      place: web::app::goals
- text: The Product refuses
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::goals
---

# Nothing to withdraw

## Trigger

The owner withdraws from a goal with nothing saved.

## Outcome

Nothing changes and the owner is told the goal is empty.
