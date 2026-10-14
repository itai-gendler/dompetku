---
kind: primary
routes:
  r: Web
steps:
- text: The Owner saves the compared statement balance
  kind: actor
  actor: owner
  entities:
  - {entity: reconciliation, effect: reads, facts: [As-of date, Statement balance, Difference]}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product keeps the Reconciliation with the app balance for that date
  kind: product
  actor: owner
  entities:
  - {entity: reconciliation, effect: creates, facts: [As-of date, Statement balance, App balance]}
  contexts:
    r:
      place: web::app::account-detail
---

# Save a reconciliation

## Trigger

After comparing, the owner taps Save reconciliation.

## Outcome

The reconciliation is kept and the account shows when it was last reconciled.
