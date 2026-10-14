---
domain: settings
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: src/lib/app-settings.server.ts#saveAppSettings
- kind: code
  role: implementation
  target: src/components/app-settings-card.tsx
---

# Change app settings

The owner sets the app's name, tagline and logo, the time zone that decides what today is, the base currency for display, the landing page, the bot's default account and the default reminder days. A cleared value falls back to the deployment's configuration or the default.
