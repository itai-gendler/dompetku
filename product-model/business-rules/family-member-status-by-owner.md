---
appliesTo:
- {type: entity, id: family-member, effect: changes, to: Inactive}
- {type: entity, id: family-member, effect: changes, to: Active}
permits:
- actors: [owner]
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#updateMember
---

# Only the owner switches family members on and off

Only the owner deactivates or reactivates a family member.
