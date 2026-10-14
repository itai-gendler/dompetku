---
domain: settings
singleton: true
references:
- kind: code
  role: implementation
  target: src/lib/app-settings-schema.ts#appSettingsInputSchema
- kind: code
  role: implementation
  target: src/lib/app-settings.server.ts#saveAppSettings
---

# App settings

The app's own settings, kept once. A missing value falls back to the deployment's configuration or the built-in default.

## Information kept

- **App name** — the name shown in the app, the login page and the browser
- **Tagline** — a short line under the name
- **Logo** — a PNG, JPEG or WebP image of at most 200 KB
- **Time zone** — decides what today is for new transactions, reminders, reports and recurring items
- **Base currency** — IDR or USD, a display preference only
- **Landing page** — whether the public landing page is shown
- **Landing tagline** — the landing page's headline
- **GitHub link** — an https link shown on public pages
- **Bot default account** — the account bot transactions use when none is named
- **Reminder days** — the default reminder window in days, 1 to 365
