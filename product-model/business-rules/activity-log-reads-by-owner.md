---
appliesTo:
- {type: entity, id: activity-entry, effect: reads}
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

# Only the owner reads the activity log

Only the owner reads the activity log.
