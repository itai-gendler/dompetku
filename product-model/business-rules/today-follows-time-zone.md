---
appliesTo:
- {type: capability, id: view-reminders}
- {type: capability, id: post-due-recurring-transactions}
- {type: entity, id: app-settings, facts: [Time zone]}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#today
---

# Today follows the configured time zone

What counts as today — for new transactions, reminders, budgets, recurring items and bot reports — follows the time zone in App settings, else the deployment's, else Asia/Jakarta.
