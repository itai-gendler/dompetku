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

# Edit gold trade

The owner changes a gold trade; its linked transaction follows, appears when an account is chosen and goes when the account is cleared.
