---
domain: transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#exportCsv
---

# Export transactions

Download a month's transactions, or all, as CSV. A family member's export holds only what they may see.
