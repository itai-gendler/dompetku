---
kind: primary
routes:
  r: Web
steps:
- text: The Owner cancels a Receivable payment and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: receivable-payment, effect: reads, facts: [Amount, Paid date]}
  - {entity: receivable, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::receivables
- text: The Product removes the Receivable payment with its linked Transaction
  kind: product
  actor: owner
  entities:
  - {entity: receivable-payment, effect: removes}
  - {entity: transaction, effect: removes, with: receivable-payment}
  contexts:
    r:
      place: web::app::receivables
---

# Cancel a payment

## Trigger

The owner cancels a payment recorded by mistake.

## Outcome

The payment and its income are gone and the remaining amount grows back.
