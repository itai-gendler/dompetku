---
id: dompetku
summary: A private, self-hosted personal finance tracker for one owner and their family, with a Telegram bot that turns chat messages and receipt photos into transactions.
category: personal-finance
tags: [personal-finance, budgeting, self-hosted, telegram-bot]
authors:
- name: Ilham Ramadhan
  url: https://github.com/ilramdhan
license: MIT
languages: [id, en]
limitations:
- 'There is no sign-up: the owner''s login comes from the deployment''s configuration, and only the owner adds family members.'
- A transaction read from a Telegram chat message or receipt photo waits as a preview until someone in that chat saves it, and reading it never creates a category.
- Amounts are kept in IDR or USD only; totals, budgets and reports are computed in IDR.
- Due recurring transactions and monthly account fees are posted the next time the dashboard, the reminders or a bot report needs them; the app runs no clock of its own.
- Reminders and reports reach Telegram or email through the owner's own n8n workflows or the configured email service; the app does not push them on a schedule.
references:
- kind: doc
  role: intent
  target: README.md
  title: README
- kind: doc
  role: context
  target: docs/ARCHITECTURE.md
  title: Architecture
- kind: doc
  role: context
  target: docs/FAQ.md
  title: FAQ
---

# Dompetku

Dompetku ("my wallet") keeps one household's money in one place: accounts and their balances,
income, expenses and transfers, budgets per category, savings goals, recurring transactions,
subscriptions, installment debts and the reminders that come from them. The owner works in the web
app and in their own Telegram bot, where a short message such as "kopi 25rb" or a receipt photo
becomes a transaction preview that is saved only when someone taps Save. Family members sign in to
the web app and see only the accounts the owner shares with them, to view or to manage. The owner's
n8n workflows use an automation API to deliver reminders, reports and backups. The interface is in
Indonesian and English.

## Intent

A private, self-hosted personal finance tracker: everything lives in the owner's own database and
deployment, "so your financial data stays yours". It is built "for you and your family", designed
with Indonesian users in mind (Rupiah, local banks and e-wallets, chat shortcuts like `25rb` and
`2jt`), and makes recording a coffee as quick as sending a chat message.
