---
kind: alternative
routes:
  r: Web
steps:
- text: The Owner chooses Replace all and types GANTI
  kind: actor
  actor: owner
  entities: []
  contexts:
    r:
      place: web::administration::backup
- text: The Product deletes every current Subscription
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: removes}
  contexts:
    r:
      place: web::administration::backup
- text: The Product deletes every current Goal
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: removes}
  contexts:
    r:
      place: web::administration::backup
- text: The Product deletes every current Budget
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: removes}
  contexts:
    r:
      place: web::administration::backup
- text: The Product deletes every current Transaction
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: removes}
  contexts:
    r:
      place: web::administration::backup
- text: The Product deletes every current Category
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: removes}
  contexts:
    r:
      place: web::administration::backup
- text: The Product deletes every current Account
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: removes}
  contexts:
    r:
      place: web::administration::backup
- text: The Product fills each Account from the file
  kind: product
  actor: owner
  entities:
  - {entity: account, effect: creates, facts: [Name, Type, Currency, Initial balance, Color, Archived, Transfer fee presets, Top-up fee presets, Monthly fee, Monthly fee day]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product fills each Category from the file
  kind: product
  actor: owner
  entities:
  - {entity: category, effect: creates, facts: [Name, Kind, Color]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product fills each Transaction from the file
  kind: product
  actor: owner
  entities:
  - {entity: transaction, effect: creates, facts: [Kind, Amount, Currency, Date, Description, Merchant, Notes, Receipt items, Receipt photos, Source, Split group]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product fills each Budget from the file
  kind: product
  actor: owner
  entities:
  - {entity: budget, effect: creates, facts: [Monthly limit, Alert percent, Rollover]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product fills each Goal from the file
  kind: product
  actor: owner
  entities:
  - {entity: goal, effect: creates, facts: [Name, Target amount, Saved amount, Deadline, Color]}
  contexts:
    r:
      place: web::administration::backup
- text: The Product fills each Subscription from the file
  kind: product
  actor: owner
  entities:
  - {entity: subscription, effect: creates, facts: [Name, Amount, Tax percent, Currency, Cycle, Interval, Active, Notes]}
  contexts:
    r:
      place: web::administration::backup
---

# Replace everything with a backup

## Trigger

The owner chooses Replace all and types GANTI.

## Outcome

All current data except sign-in details is replaced by the file's.
