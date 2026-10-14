---
kind: primary
routes:
  r: Web
steps:
- text: The Owner picks 6 or 12 months and reads spending per Category
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Amount in IDR, Date]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::reports
---

# See category trends

## Trigger

The owner opens Reports.

## Outcome

Monthly spending per category for the chosen range is shown.
