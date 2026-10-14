---
appliesTo:
- {type: entity, id: recurring-transaction, effect: reads}
permits:
- actors: [owner]
- unattended: true
references:
- kind: code
  role: implementation
  target: src/lib/server-fn-access.ts#SERVER_FN_ACCESS
- kind: code
  role: implementation
  target: src/lib/permissions.ts#can
---

# Only the owner sees recurring transactions

Recurring transactions are the owner's; the Product reads them when posting due occurrences.
