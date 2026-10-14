---
appliesTo:
- {type: entity, id: installment-payment, effect: removes}
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

# Only the owner removes installment payments

Only the owner removes installment payments; family members cannot, and the Telegram bot acts for the owner.
