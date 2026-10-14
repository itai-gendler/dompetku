---
appliesTo:
- {type: entity, id: pocket, effect: reads}
permits:
- actors: [owner]
- related:
  - {verb: contains, entity: account}
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
references:
- kind: code
  role: implementation
  target: src/lib/pockets.functions.ts
---

# Who sees pockets

The owner sees every pocket; a family member sees the pockets of accounts shared with them.
