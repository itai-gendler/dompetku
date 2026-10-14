---
availability:
- place: web::app
- place: telegram-bot
- place: automation-api
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeReminders
- kind: code
  role: implementation
  target: src/routes/_app/reminders.tsx
- kind: code
  role: implementation
  target: src/routes/api/public/n8n/reminders.ts
---

# View reminders

List what needs attention within a window of days: unpaid installments and active subscriptions due (or overdue), manual recurring items due, monthly account fees coming, and budgets past their warning this month. The web page offers 7, 30 or 90 days (30 first); the bot's /tagihan uses the days given, else the Settings reminder days, else 14; the automation API uses the days asked, else the Settings reminder days, else 7.
