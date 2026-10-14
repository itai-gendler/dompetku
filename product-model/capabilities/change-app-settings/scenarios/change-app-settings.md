---
kind: primary
routes:
  r: Web
steps:
- text: The Owner changes the settings and saves
  kind: actor
  actor: owner
  entities:
  - {entity: app-settings, effect: reads, facts: [App name, Time zone, Bot default account, Reminder days]}
  contexts:
    r:
      place: web::administration::app-settings
- text: The Product keeps the App settings
  kind: product
  actor: owner
  entities:
  - {entity: app-settings, effect: changes, facts: [App name, Tagline, Logo, Time zone, Base currency, Landing page, Landing tagline, GitHub link, Bot default account, Reminder days]}
  contexts:
    r:
      place: web::administration::app-settings
---

# Change app settings

## Trigger

The owner edits App settings and saves.

## Outcome

The new settings apply within about a minute everywhere, including the bot and reminders.
