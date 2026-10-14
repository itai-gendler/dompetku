---
domain: receivables
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/receivables.tsx
- kind: code
  role: implementation
  target: src/lib/assets.server.ts
---

# Create receivable

The owner records money lent to someone. With an account chosen, the loan is also an expense in category Piutang from that account; net worth adds the outstanding amount back as an asset.
