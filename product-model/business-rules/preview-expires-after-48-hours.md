---
appliesTo:
- {type: capability, id: accept-transaction-preview}
- {type: capability, id: edit-transaction-preview}
- {type: entity, id: transaction-preview}
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts
---

# A preview expires after 48 hours

A preview older than 48 hours cannot be saved or edited; tapping one of its buttons closes it, and a message after that is read as a new transaction.
