---
entities:
- {entity: transaction-preview, shows: [Kind, Amount, Currency, Category, Account, Date, Description, Merchant, Receipt items, Pocket tag, Read by]}
- {entity: category, shows: [Name]}
- {entity: account, shows: [Name]}
references:
- kind: code
  role: implementation
  target: src/lib/bot.ts#previewText
- kind: code
  role: implementation
  target: src/lib/bot.ts#previewKeyboard
---

# Transaction preview

The preview message with Save, Cancel, Category, Account, In/Out and Description buttons, telling whether it was read without AI or by AI.
