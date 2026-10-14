---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Category and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: category, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::categories
- text: The Product removes the Category and its Budget
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: removes}
  - {entity: budget, effect: removes, with: category}
  contexts:
    r:
      place: web::administration::categories
---

# Delete a category

## Trigger

The owner deletes a category and confirms.

## Outcome

The category and its budget are gone; its transactions stay without a category.
