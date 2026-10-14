---
appliesTo:
- {type: entity, id: transaction, effect: reads}
permits:
- actors: [owner]
- actors: [n8n-automation]
- related:
  - {verb: holds, entity: account}
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
- related:
  - {verb: receives, entity: account}
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#canViewTx
---

# Who sees transactions

The owner and the owner's n8n workflows see every transaction; a family member sees a transaction that leaves or enters an account shared with them, at either level.
