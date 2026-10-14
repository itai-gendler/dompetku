---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the Category
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: [Name, Kind, Color]}
  contexts:
    r:
      place: web::administration::categories
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: changes, facts: [Name, Kind, Color]}
  contexts:
    r:
      place: web::administration::categories
---

# Edit a category

## Trigger

The owner edits a category.

## Outcome

Every transaction in the category shows the new name.
