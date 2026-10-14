---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#applyMonthlyFees
- kind: code
  role: implementation
  target: src/lib/fees.ts
---

# Post monthly account fees

An account with a monthly fee gets that fee recorded as an expense in category Biaya Admin once a month, on its fee day. It runs when the dashboard, the reminders or a bot report next needs it.
