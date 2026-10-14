---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Receivable
  kind: actor
  actor: owner
  entities:
  - {entity: receivable, effect: reads, facts: [Purpose, Borrower, Due date]}
  contexts:
    r:
      place: web::app::receivables
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: receivable, effect: changes, facts: [Purpose, Borrower, Due date, Notes]}
  contexts:
    r:
      place: web::app::receivables
---

# Edit a receivable

## Trigger

The owner corrects the borrower or due date.

## Outcome

The receivable shows the new details.
