---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Goal
  kind: actor
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: [Name, Target amount, Saved amount, Deadline]}
  contexts:
    r:
      place: web::app::goals
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: changes, facts: [Name, Target amount, Saved amount, Deadline, Color]}
  contexts:
    r:
      place: web::app::goals
---

# Edit a goal

## Trigger

The owner edits a goal.

## Outcome

The goal and its projection follow the new values; no money moves.
