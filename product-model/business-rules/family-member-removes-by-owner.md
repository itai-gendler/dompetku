---
appliesTo:
- {type: entity, id: family-member, effect: removes}
permits:
- actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#deleteMember
---

# Only the owner removes family members

Only the owner removes family members. The owner is never a family member, so never changed or removed here.
