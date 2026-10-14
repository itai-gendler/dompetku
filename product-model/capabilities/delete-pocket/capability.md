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

# Delete pocket

Delete a pocket; its transactions stay, without a pocket.
