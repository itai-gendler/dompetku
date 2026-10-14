---
appliesTo:
- {type: entity, id: receivable, effect: reads}
permits:
- actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/server-fn-access.ts#SERVER_FN_ACCESS
- kind: code
  role: implementation
  target: src/lib/permissions.ts#can
---

# Only the owner sees receivables

Receivables are the owner's.
