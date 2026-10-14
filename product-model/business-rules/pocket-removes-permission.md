---
appliesTo:
- {type: entity, id: pocket, effect: removes}
permits:
- actors: [owner]
- related:
  - {verb: contains, entity: account}
  - {verb: grants, entity: wallet-access}
  - {verb: holds, entity: family-member}
  when:
  - {entity: wallet-access, fact: Level, is: Manage}
references:
- kind: code
  role: implementation
  target: src/lib/pockets.functions.ts
---

# Who deletes pockets

The owner deletes any pocket; a family member deletes pockets only on an account where they hold Manage.
