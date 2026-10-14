---
kind: primary
routes:
  r: Web
steps:
- text: The Owner picks a year and reads the recap per Category
  kind: actor
  actor: owner
  entities:
  - {entity: transaction, effect: reads, facts: [Amount in IDR, Date]}
  - {entity: category, effect: reads, facts: [Name]}
  contexts:
    r:
      place: web::app::yearly-recap
---

# See a year's recap

## Trigger

The owner opens Yearly recap.

## Outcome

Income, expense and spending per category for each month of the year are shown, ready to print or export.
