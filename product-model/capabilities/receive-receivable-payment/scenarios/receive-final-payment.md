---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner enters the last payment
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: [Remaining]}
  contexts:
    r:
      place: web::app::receivables
- text: The Product keeps the Receivable payment and marks the Receivable paid
  kind: product
  actor: owner
  entities:
  - {entity: receivable-payment, effect: creates, facts: [Amount, Paid date]}
  - {entity: receivable, effect: changes, from: Active, to: Paid, facts: []}
  contexts:
    r:
      place: web::app::receivables
---

# Receive the final payment

## Trigger

A payment brings the total received to the amount lent.

## Outcome

The receivable is paid and leaves the outstanding total.
