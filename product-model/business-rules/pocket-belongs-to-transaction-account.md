---
appliesTo:
- {type: capability, id: record-transaction}
- {type: capability, id: edit-transaction}
- {type: capability, id: accept-transaction-preview}
- {type: entity, id: transaction, effect: creates}
references:
- kind: code
  role: implementation
  target: src/lib/pockets.server.ts#assertPocketForTx
---

# A transaction's pocket belongs to its account

A transaction can carry only a pocket of its own source account; an archived pocket cannot be newly picked, and only an expense, an income or the outgoing side of a transfer carries a pocket. A bot #tag that names no pocket of the account is ignored.
