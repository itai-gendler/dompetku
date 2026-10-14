---
kind: primary
routes:
  r: Web
steps:
- text: The Owner deletes the Pocket and confirms
  kind: actor
  actor: owner
  entities:
  - {entity: pocket, effect: reads, facts: []}
  contexts:
    r:
      place: web::app::account-detail
- text: The Product removes the Pocket
  kind: product
  actor: owner
  entities:
  - {entity: pocket, effect: removes}
  contexts:
    r:
      place: web::app::account-detail
---

# Delete a pocket

## Trigger

The owner deletes a pocket and confirms.

## Outcome

The pocket is gone and its transactions remain on the account without a pocket.
