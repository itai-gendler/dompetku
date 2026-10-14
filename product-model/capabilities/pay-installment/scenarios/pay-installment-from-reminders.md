---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner taps Pay on a due Debt installment
  kind: actor
  actor: owner
  entities:
  - {entity: debt, effect: reads, facts: [Name, Installment amount, Next due date]}
  contexts:
    r:
      place: web::app::reminders
- text: The Product records the expense and the Installment payment
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Amount in IDR, Date, Description, Merchant, Source], with: installment-payment}
  - {entity: installment-payment, effect: creates, facts: [Installment number, Amount, Paid date]}
  contexts:
    r:
      place: web::app::reminders
---

# Pay an installment from Reminders

## Trigger

An installment is due and the owner taps Pay in Reminders.

## Outcome

The installment is paid and leaves the reminders.
