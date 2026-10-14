---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner cancels a payment of a paid Receivable
  kind: actor
  actor: owner
  entities:
  - {entity: receivable-payment, effect: reads, facts: [Amount]}
  - {entity: receivable, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::receivables
- text: The Product removes the Receivable payment with its Transaction and marks the Receivable active
  kind: product
  actor: owner
  entities:
  - {entity: receivable-payment, effect: removes}
  - {entity: transaction, effect: removes, with: receivable-payment}
  - {entity: receivable, effect: changes, from: Paid, to: Active, facts: []}
  contexts:
    r:
      place: web::app::receivables
---

# Cancel a payment of a paid receivable

## Trigger

The owner cancels a payment on a receivable marked paid.

## Outcome

The receivable is active again with the cancelled amount remaining.
