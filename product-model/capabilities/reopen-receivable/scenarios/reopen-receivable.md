---
kind: primary
routes:
  r: Web
steps:
- text: The Owner reopens the Receivable
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::receivables
- text: The Product marks it active
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: changes, from: Paid, to: Active, facts: []}
  contexts:
    r:
      place: web::app::receivables
---

# Reopen a receivable

## Trigger

The owner taps Reopen and confirms.

## Outcome

The receivable is active again with its remaining amount.
