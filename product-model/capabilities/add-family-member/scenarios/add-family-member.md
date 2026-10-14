---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters a username, an optional full name and a temporary password
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::family-members
- text: The Product creates the Family member, active and required to change the password, with that Profile
  kind: product
  actor: owner
  entities:
  - {entity: family-member, effect: creates, to: Active, facts: [Must change password]}
  - {entity: profile, effect: creates, facts: [Username, Display name, Password], with: family-member}
  contexts:
    r:
      place: web::administration::family-members
---

# Add a family member

## Trigger

The owner adds a family member.

## Outcome

An active member exists who must change the temporary password at first sign-in and sees no accounts until access is given.
