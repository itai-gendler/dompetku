---
appliesTo:
- {type: entity, id: gold-trade, effect: reads}
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

# Only the owner sees gold

Gold trades and holdings are the owner's.
