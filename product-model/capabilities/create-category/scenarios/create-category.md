---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters a name, kind and color
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::categories
- text: The Product keeps the new Category
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: creates, facts: [Name, Kind, Color]}
  contexts:
    r:
      place: web::administration::categories
---

# Add a category

## Trigger

The owner adds a category.

## Outcome

The category can be picked for transactions, budgets and bot previews.
