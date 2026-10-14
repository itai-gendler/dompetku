---
appliesTo:
- {type: entity, id: recurring-transaction, effect: changes}
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

# Who changes recurring transactions

The owner changes, pauses, resumes and records recurring transactions; the Product moves an automatic schedule on, and pauses it at its end date, when it posts due occurrences.
