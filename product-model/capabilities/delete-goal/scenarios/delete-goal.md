---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Goal and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::goals
- text: The Product removes the Goal
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: removes}
  contexts:
    r:
      place: web::app::goals
---

# Delete a goal

## Trigger

The owner deletes a goal and confirms.

## Outcome

The goal is gone; transfers recorded for it remain.
