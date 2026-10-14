---
domain: receivables
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#deleteReceivablePayment
---

# Cancel receivable payment

The owner removes a recorded payment together with its income; the receivable is active again.
