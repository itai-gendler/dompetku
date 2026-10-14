---
appliesTo:
- {type: capability, id: accept-transaction-preview}
- {type: capability, id: dismiss-transaction-preview}
- {type: entity, id: transaction-preview}
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts
---

# Only someone in the preview's chat saves or cancels it

A preview is saved or cancelled only from the chat it was made in; a button naming a preview of another chat finds nothing.
