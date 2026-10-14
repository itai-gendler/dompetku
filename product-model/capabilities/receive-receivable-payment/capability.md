---
domain: receivables
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#payReceivable
---

# Receive receivable payment

The owner records money coming back, in part or in full. With an account, it is also an income in category Piutang. When the payments reach the amount lent, the receivable is paid.
