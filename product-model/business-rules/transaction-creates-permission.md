---
appliesTo:
- {type: entity, id: transaction, effect: creates}
permits:
- actors: [owner]
- related:
  - {verb: holds, entity: account}
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
  when:
  - {entity: wallet-access, fact: Level, is: Manage}
- actors: [n8n-automation]
- unattended: true
references:
- kind: code
  role: implementation
  target: src/lib/permissions.ts#canWriteTx
- kind: code
  role: implementation
  target: src/lib/rbac.server.ts#assertTxWrite
---

# Who records transactions

The owner records any transaction; a family member records a transaction only on an account where they hold Manage. The owner's n8n workflows record transactions, and the Product records due recurring occurrences and monthly fees on its own.
