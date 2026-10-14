---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/pockets.functions.ts
- kind: code
  role: implementation
  target: src/lib/pockets.server.ts
- kind: code
  role: implementation
  target: src/components/account-pockets.tsx
---

# Edit pocket

Change a pocket's name, amount, threshold, period or archive mark; its account never changes.
