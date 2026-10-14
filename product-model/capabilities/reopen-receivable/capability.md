---
domain: receivables
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#setReceivableStatus
---

# Reopen receivable

The owner reopens a paid receivable.
