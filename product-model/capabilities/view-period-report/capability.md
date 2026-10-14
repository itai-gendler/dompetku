---
availability:
- place: telegram-bot
- place: automation-api
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#reportData
- kind: code
  role: implementation
  target: src/routes/api/public/n8n/report.ts
---

# View period report

A short report for today, yesterday, this or last week, this or last month or a given month: income, expense, the change against the previous period, the daily average, spending per category and the three largest expenses. The bot answers /hariini, /kemarin, /minggu, /bulan and /bulanlalu; n8n schedules fetch it for daily, weekly and monthly messages.
