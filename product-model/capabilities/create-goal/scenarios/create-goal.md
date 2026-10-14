---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the name, target, amount saved so far, deadline and savings Account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::goals
- text: The Product keeps the Goal
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: creates, facts: [Name, Target amount, Saved amount, Deadline, Color]}
  contexts:
    r:
      place: web::app::goals
---

# Add a goal

## Trigger

The owner adds a goal.

## Outcome

The goal shows its progress, the amount to save per month and week before the deadline, and an estimated completion month.
