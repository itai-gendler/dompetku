---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the statement date and closing balance of the Account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product works out the balance at the end of that date and the difference
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Kind, Amount, Date]}
  contexts:
    r:
      place: web::app::account-detail
---

# Compare a closing balance

## Trigger

The owner enters the statement date and closing balance and taps Compare.

## Outcome

The app balance for that date and the difference are shown; a zero difference reads as matching.
