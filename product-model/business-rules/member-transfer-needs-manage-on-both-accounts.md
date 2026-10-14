---
appliesTo:
- {type: capability, id: record-transaction}
- {type: capability, id: edit-transaction}
- {type: entity, id: transaction, effect: creates}
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#canWriteTx
---

# A family member's transfer needs Manage on both accounts

A family member records, edits or deletes a transfer only when they hold Manage on the source and the destination account. A transaction without an account is the owner's alone.
