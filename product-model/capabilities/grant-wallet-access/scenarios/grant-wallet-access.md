---
kind: primary
routes:
  r: Web
steps:
- text: The Owner picks View or Manage for an Account the Family member cannot see yet and saves
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name]}
  - {entity: family-member, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::family-members
- text: The Product keeps the Wallet access for that Family member
  kind: product
  actor: owner
  entities:
  - {entity: wallet-access, effect: creates, facts: [Level]}
  - {entity: family-member, effect: reads, facts: []}
  contexts:
    r:
      place: web::administration::family-members
---

# Share an account with a member

## Trigger

The owner sets an account from No access to View or Manage for a member and saves.

## Outcome

The member sees that account right away and, with Manage, records on it.
