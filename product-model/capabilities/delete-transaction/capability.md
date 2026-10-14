---
domain: transactions
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/split.functions.ts#deleteTransaction
- kind: code
  role: implementation
  target: src/lib/split.server.ts
---

# Delete transaction

Delete a transaction, or every part of a split at once. Receipt photos go when no other transaction still uses them.
