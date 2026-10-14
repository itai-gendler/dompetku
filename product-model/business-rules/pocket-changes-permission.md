---
appliesTo:
- {type: entity, id: pocket, effect: changes}
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

# Who edits pockets

The owner edits any pocket; a family member edits pockets only on an account where they hold Manage.
