---
appliesTo:
- {type: entity, id: debt, effect: reads}
permits:
- actors: [owner]
- actors: [n8n-automation]
references:
- kind: code
  role: implementation
  target: src/lib/server-fn-access.ts#SERVER_FN_ACCESS
- kind: code
  role: implementation
  target: src/lib/permissions.ts#can
---

# Only the owner sees debts

Debts are the owner's; the owner's n8n workflows read them for reminders.
