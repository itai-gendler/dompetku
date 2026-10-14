---
domain: accounts
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/routes/_app/accounts.tsx
- kind: code
  role: implementation
  target: src/lib/finance.functions.ts#saveRow
---

# Edit account

The owner changes an account's details, including archiving it.
