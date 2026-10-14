---
domain: transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#updateTransaction
- kind: code
  role: implementation
  target: src/lib/rbac.server.ts#assertTxIdWrite
---

# Edit transaction

Change a recorded transaction. A family member needs Manage on its accounts, before and after the change.
