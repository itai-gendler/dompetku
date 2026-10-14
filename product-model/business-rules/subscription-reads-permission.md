---
appliesTo:
- {type: entity, id: subscription, effect: reads}
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

# Only the owner sees subscriptions

Subscriptions are the owner's; the owner's n8n workflows read them for reminders.
