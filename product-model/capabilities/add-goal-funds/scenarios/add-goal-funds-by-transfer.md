---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters an amount and picks the Account it comes from
  kind: actor
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: [Name, Saved amount]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::goals
- text: The Goal has a savings account other than the chosen one
  kind: condition
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: []}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::goals
- text: The Product records a transfer into the savings account and raises the saved amount
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Notes, Source]}
  - {entity: goal, effect: changes, facts: [Saved amount]}
  - {entity: account, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::goals
---

# Add funds by transfer

## Trigger

The owner adds an amount to a goal from another account.

## Outcome

The saved amount grows and a transfer from the chosen account to the goal's savings account is recorded.
