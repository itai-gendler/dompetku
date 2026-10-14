---
kind: primary
routes:
  r: Web
steps:
- text: The Owner enters the name, type, currency, initial balance and any fees
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::app::accounts
- text: The Product keeps the new Account
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: creates, facts: [Name, Type, Currency, Initial balance, Color, Archived, Transfer fee presets, Top-up fee presets, Monthly fee, Monthly fee day]}
  contexts:
    r:
      place: web::app::accounts
---

# Add an account

## Trigger

The owner adds an account.

## Outcome

The account is listed with a balance equal to its initial balance.
