---
appliesTo:
- {type: entity, id: account, effect: reads}
permits:
- actors: [owner]
- actors: [n8n-automation]
- unattended: true
- related:
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#allowedAccountIds
---

# Who sees accounts

The owner and the owner's n8n workflows see every account, and the Product reads them when posting monthly fees; a family member sees only the accounts shared with them.
