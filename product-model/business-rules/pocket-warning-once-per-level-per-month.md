---
appliesTo:
- {type: capability, id: record-transaction}
- {type: capability, id: accept-transaction-preview}
- {type: capability, id: edit-transaction}
- {type: entity, id: pocket}
references:
- kind: code
  role: implementation
  target: src/lib/pockets.server.ts#pocketAlertsFor
---

# Each pocket warns at most once per level per month

A pocket warns when a save takes it to its low-balance threshold (low) or to zero (empty), at most once per level per month, and only for transactions dated in the current period.
