---
appliesTo:
- {type: entity, id: transaction, effect: changes}
permits:
- actors: [owner]
- related:
  - {verb: holds, entity: account}
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
  when:
  - {entity: wallet-access, fact: Level, is: Manage}
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#canWriteTx
- kind: code
  role: implementation
  target: src/lib/rbac.server.ts#assertTxWrite
---

# Who edits transactions

The owner edits any transaction; a family member edits a transaction only on an account where they hold Manage.
