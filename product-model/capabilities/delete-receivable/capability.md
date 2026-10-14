---
domain: receivables
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#deleteReceivable
---

# Delete receivable

The owner deletes a receivable with its payments and the transactions recorded for them.
