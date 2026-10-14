---
appliesTo:
- {type: capability, id: create-transaction-preview}
- {type: capability, id: edit-transaction-preview}
- {type: entity, id: transaction-preview}
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts
---

# A transaction preview changes nothing until it is saved

Reading a message or receipt and editing the preview record no transaction and move no balance; only Save does.
