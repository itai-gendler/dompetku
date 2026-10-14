---
domain: gold
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/gold.tsx
- kind: code
  role: implementation
  target: src/lib/assets.server.ts#saveGold
---

# Record gold trade

The owner records buying or selling gold. With an account chosen, a buy is also recorded as an expense and a sale as an income in category Emas, so net worth counts the gold once.
