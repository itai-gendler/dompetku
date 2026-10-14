---
kind: primary
routes:
  r: Web
steps:
- text: The Owner marks the Receivable paid
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::receivables
- text: The Product marks it paid
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: changes, from: Active, to: Paid, facts: []}
  contexts:
    r:
      place: web::app::receivables
---

# Mark a receivable paid

## Trigger

The owner taps Mark paid and confirms.

## Outcome

The receivable is paid and leaves the outstanding total.
