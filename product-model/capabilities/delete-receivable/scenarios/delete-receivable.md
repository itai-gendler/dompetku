---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Receivable and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::receivables
- text: The Product removes the Receivable with each Receivable payment and the linked transactions
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: removes, from: Active}
  - {entity: receivable-payment, effect: removes, with: receivable}
  - {entity: transaction, as: loan, effect: removes, with: receivable}
  - {entity: transaction, as: repayment, effect: removes, with: receivable-payment}
  contexts:
    r:
      place: web::app::receivables
---

# Delete a receivable

## Trigger

The owner deletes a receivable and confirms.

## Outcome

The receivable, its payments and their linked transactions are gone.
