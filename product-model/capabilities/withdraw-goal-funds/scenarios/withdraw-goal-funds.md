---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters an amount and picks the Account it goes to
  kind: actor
  actor: owner
  entities:
  - {entity: goal, effect: reads, facts: [Saved amount]}
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::goals
- text: The Product caps the amount at the saved amount, records the transfer and lowers the saved amount
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Notes, Source]}
  - {entity: goal, effect: changes, facts: [Saved amount]}
  contexts:
    r:
      place: web::app::goals
---

# Withdraw funds

## Trigger

The owner withdraws from a goal into another account.

## Outcome

The saved amount drops by the amount, capped at what was saved, and a transfer out of the savings account is recorded.
