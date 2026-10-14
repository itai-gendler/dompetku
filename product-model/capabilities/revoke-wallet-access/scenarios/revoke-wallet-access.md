---
kind: primary
routes:
  r: Web
steps:
- text: The Owner sets the Wallet access to No access and saves
  kind: actor
  actor: owner
  entities:
  - {entity: wallet-access, effect: reads, facts: [Level]}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product removes the Wallet access
  kind: product
  actor: owner
  entities:
  - {entity: wallet-access, effect: removes}
  contexts:
    r:
      place: web::administration::family-members
---

# Stop sharing an account

## Trigger

The owner sets an account to No access for a member and saves.

## Outcome

The member no longer sees that account; transfers touching it show the other side as Other wallet.
