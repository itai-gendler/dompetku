---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner enters an amount without an account
  kind: actor
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: [Saved amount]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::goals
- text: The Product raises the saved amount of the Goal
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: changes, facts: [Saved amount]}
  contexts:
    r:
      place: web::app::goals
---

# Add funds without an account

## Trigger

The owner adds an amount without choosing an account, or the goal has no savings account.

## Outcome

Only the saved amount grows; no transaction is recorded.

## Edge cases

- The saved amount may go past the target.
