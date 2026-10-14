---
kind: validation
routes:
  r: Web
steps:
- text: The Owner picks a CSV file with unreadable rows
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
- text: The Product leaves the unreadable rows out of the import
  kind: product
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::transactions
---

# Rows that cannot be read

## Trigger

Some rows have a bad date, type or amount.

## Outcome

Those rows are listed as invalid in the preview and never imported.
