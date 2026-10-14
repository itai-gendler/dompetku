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

# Create pocket

Earmark part of one account's money as a pocket. The owner, or a member with Manage on the account, adds it.
