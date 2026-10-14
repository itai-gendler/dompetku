---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the details of the Account
  kind: actor
  actor: owner
  entities:
  - {entity: account, effect: reads, facts: [Name, Type, Currency]}
  contexts:
    r:
      place: web::app::accounts
- text: The Product keeps the changes
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: changes, facts: [Name, Type, Currency, Initial balance, Color, Transfer fee presets, Top-up fee presets, Monthly fee, Monthly fee day]}
  contexts:
    r:
      place: web::app::accounts
---

# Edit an account

## Trigger

The owner edits an account.

## Outcome

The account shows the new details; its balance follows a changed initial balance.
