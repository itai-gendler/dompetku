---
appliesTo:
- {type: capability, id: accept-transaction-preview}
- {type: capability, id: record-transaction}
- {type: entity, id: transaction, effect: creates}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#createFromExternal
---

# Saving the same preview or key twice records one transaction

A preview saved twice, and a transaction posted to the automation API with a key already used, return the transaction recorded the first time.
