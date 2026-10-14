---
appliesTo:
- {type: entity, id: installment-payment, effect: creates}
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

# Only the owner creates installment payments

Only the owner creates installment payments; family members cannot, and the Telegram bot acts for the owner.
