---
domain: settings
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#can
- kind: code
  role: implementation
  target: src/lib/users.server.ts#setMemberPermissions
---

# Wallet access

One account shared with one family member, at one level. A member without any wallet access sees no accounts or transactions.

## Information kept

- **Level** — View (see the account, its balance, transactions, pockets and report) or Manage (also record, edit and delete its transactions and manage its pockets)
