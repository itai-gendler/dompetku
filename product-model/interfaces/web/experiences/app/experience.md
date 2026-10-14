---
access: authenticated
actors: [owner, family-member]
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#canOpenPath
---

# App

The signed-in app. A family member reaches only the dashboard, transactions, accounts, account
details, reports and their profile, scoped to the accounts shared with them; every other page is
the owner's.
