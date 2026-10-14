---
appliesTo:
- {type: capability, id: browse-transactions}
- {type: capability, id: export-transactions}
- {type: capability, id: view-dashboard}
- {type: entity, id: transaction, effect: reads}
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#maskTx
---

# An unshared account shows as Other wallet

When a family member sees a transfer to or from an account not shared with them, that side reads Other wallet and its pocket is hidden; its name and identity never reach the member, in lists, dashboards and exports alike.
