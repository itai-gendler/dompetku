---
kind: primary
routes:
  r: Web
steps:
- text: The Family member changes the display name, address or photo
  kind: actor
  actor: family-member
  entities:
  - {entity: profile, effect: reads, facts: [Display name, Address, Profile photo]}
  contexts:
    r:
      place: web::app::profile
- text: The Product keeps the new details
  kind: product
  actor: family-member
  entities:
  - {entity: profile, effect: changes, facts: [Display name, Address, Profile photo]}
  contexts:
    r:
      place: web::app::profile
---

# Edit one's own profile

## Trigger

A signed-in person updates their profile.

## Outcome

The new name, address and photo are kept and shown in the app.
