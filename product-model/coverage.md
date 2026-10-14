---
scope: The Dompetku web app, Telegram bot and n8n automation API at the pinned commit.
method: Static reading of routes, server functions, server modules, schema and documentation; no code was run.
covered:
- description: Signed-in app pages for dashboard, transactions, reports, recap, accounts, budgets, goals, recurring items, subscriptions, debts, reminders, profile and settings.
  paths:
  - src/routes/_app/
  - src/routes/_app.tsx
  - src/routes/login.tsx
- description: Server functions, permission model and finance, budget, goal, recurring, subscription, pocket, member and settings logic.
  paths:
  - src/lib/finance.functions.ts
  - src/lib/finance.server.ts
  - src/lib/permissions.ts
  - src/lib/rbac.server.ts
  - src/lib/server-fn-access.ts
  - src/lib/auth.functions.ts
  - src/lib/users.server.ts
  - src/lib/users.functions.ts
  - src/lib/profile.functions.ts
  - src/lib/budget.ts
  - src/lib/budget.server.ts
  - src/lib/goals.ts
  - src/lib/recurring.ts
  - src/lib/recurring.server.ts
  - src/lib/recurring.functions.ts
  - src/lib/pockets.ts
  - src/lib/pockets.server.ts
  - src/lib/pockets.functions.ts
  - src/lib/split.server.ts
  - src/lib/split.functions.ts
  - src/lib/subscriptions.ts
  - src/lib/fees.ts
  - src/lib/schemas.ts
  - src/lib/app-settings.server.ts
  - src/lib/integrations.server.ts
  - src/lib/integrations.ts
  - src/lib/password.ts
  - src/lib/login-throttle.ts
  - src/lib/totp.server.ts
- description: Telegram bot parsing, previews, commands, group mode, AI quota and receipt reading.
  paths:
  - src/lib/bot.ts
  - src/lib/bot.server.ts
  - src/lib/bot-group.ts
  - src/lib/ai-usage.server.ts
  - src/lib/ocr.server.ts
  - src/lib/telegram.server.ts
- description: Automation and Telegram webhook endpoints.
  paths:
  - src/routes/api/public/n8n/
  - src/routes/api/public/telegram/
  - src/lib/api-key.server.ts
- description: Form and card components that carry product behavior.
  paths:
  - src/components/transaction-dialog.tsx
  - src/components/account-pockets.tsx
  - src/components/users-card.tsx
  - src/components/app-settings-card.tsx
  - src/components/integrations-card.tsx
  - src/components/split-editor.tsx
- description: Database schema.
  paths:
  - supabase/schema.sql
- description: Gold trades, gold prices and receivables.
  paths:
  - src/lib/assets.ts
  - src/lib/assets.server.ts
  - src/routes/_app/gold.tsx
  - src/components/assets-overview.tsx
- description: Per-account report, statement comparison and reconciliation.
  paths:
  - src/lib/account-report.ts
  - src/lib/account-report.server.ts
  - src/lib/account-report.functions.ts
  - src/components/account-reconcile.tsx
- description: CSV import with preview and duplicate detection.
  paths:
  - src/lib/csv.ts
  - src/components/csv-import.tsx
- description: Backup restore in merge and replace modes.
  paths:
  - src/lib/backup.ts
  - src/lib/backup.server.ts
  - src/lib/backup.functions.ts
  - src/components/backup-restore.tsx
- description: Privacy mode and language on the device.
  paths:
  - src/lib/privacy.ts
  - src/lib/privacy-sync.tsx
  - src/lib/i18n.tsx
  - src/lib/lang.ts
exclusions:
- description: UI kit, charts, skeletons, layout shell, fonts, icons and static assets.
  paths:
  - src/components/ui/
  - src/components/charts/
  - src/components/skeletons.tsx
  - src/components/app-shell.tsx
  - public/
- description: Build, deployment, CI, dev database, screenshot and branding scripts.
  paths:
  - scripts/
  - .github/
  - .devcontainer/
  - Dockerfile
  - docker-compose.yml
  - vite.config.ts
  - vercel.json
  - .lovable/
- description: Tests, used as leads only.
  paths:
  - src/test/
- description: Monitoring and error reporting.
  paths:
  - src/lib/monitoring.ts
  - src/lib/monitoring.server.ts
  - src/lib/error-capture.ts
  - src/lib/lovable-error-reporting.ts
- description: 'Public demo deployment (guards, credentials, daily reset): peripheral demo tooling.'
  paths:
  - src/lib/demo.ts
  - src/lib/demo.server.ts
  - src/components/demo.tsx
  - src/components/demo-gate.tsx
- description: 'Two-step enrolment helper: it only displays a secret for the deployment''s configuration and keeps nothing.'
  paths:
  - src/components/two-factor-card.tsx
- description: 'App version check against GitHub releases: maintenance plumbing.'
  paths:
  - src/lib/version.server.ts
  - src/lib/version.ts
  - src/components/version-badge.tsx
- description: 'n8n workflow templates: the schedules belong to n8n, another system; the endpoints they call are mapped.'
  paths:
  - n8n/
- description: 'Theme switching: visual design only.'
  paths:
  - src/routes/__root.tsx
unmapped:
- description: 'Public landing, privacy and terms pages and their search-engine files: marketing and legal text for visitors, kept no product data.'
  paths:
  - src/routes/index.tsx
  - src/routes/privacy.tsx
  - src/routes/terms.tsx
  - src/routes/llms[.]txt.ts
  - src/routes/robots[.]txt.ts
  - src/routes/sitemap[.]xml.ts
  - src/components/landing/
  - src/components/legal/
  - src/lib/seo.ts
  - src/lib/landing.ts
- description: 'Telegram webhook registration in Settings: the registration is state Telegram keeps, not Dompetku.'
  paths:
  - src/lib/integrations.functions.ts
limitations:
- description: Exchange-rate source and fallback when the daily USD rate cannot be fetched.
  paths:
  - src/lib/finance.server.ts
---

# Coverage
