---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the full name of the Family member
  kind: actor
  actor: owner
  entities:
  - {entity: family-member, effect: reads, facts: []}
  - {entity: profile, effect: reads, facts: [Display name]}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product keeps the new name
  kind: product
  actor: owner
  entities:
  - {entity: profile, effect: changes, facts: [Display name]}
  contexts:
    r:
      place: web::administration::family-members
---

# Change a member's full name

## Trigger

The owner corrects a member's name.

## Outcome

The member is shown with the new name.
