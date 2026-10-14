---
entities:
- {entity: account, shows: [Name, Type, Currency, Balance, Archived, Monthly fee, Monthly fee day], collects: [Name, Type, Currency, Initial balance, Color, Archived, Transfer fee presets, Top-up fee presets, Monthly fee, Monthly fee day]}
entryPoints:
- web: /accounts
references:
- kind: code
  role: implementation
  target: src/routes/_app/accounts.tsx
---

# Accounts

Every account with its balance, and the form to add or edit one.
