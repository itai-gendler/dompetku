---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/account-report.server.ts#saveReconciliation
---

# Save reconciliation

The owner keeps a compared statement balance in the account's reconciliation history.
