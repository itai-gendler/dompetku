---
appliesTo:
- {type: capability, id: create-transaction-preview}
- {type: capability, id: scan-receipt}
- {type: entity, id: category}
references:
- kind: code
  role: implementation
  target: src/lib/ocr.server.ts
- kind: code
  role: implementation
  target: src/lib/bot.ts#matchCategory
---

# AI readings use only existing categories and accounts

Whatever the language model reads is matched onto existing categories (falling back to Lainnya) and existing accounts; reading never creates either.
