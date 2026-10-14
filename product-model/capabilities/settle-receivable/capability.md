---
domain: receivables
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#setReceivableStatus
---

# Settle receivable

The owner marks a receivable paid without further payments, for example when the rest is forgiven.
