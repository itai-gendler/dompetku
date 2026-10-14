---
appliesTo:
- {type: entity, id: family-member, effect: changes, facts: [Must change password]}
permits:
- actors: [owner]
- self: true
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#resetMemberPassword
---

# Who sets and clears the need to change a password

The owner sets it by giving a temporary password; the member clears it by choosing their own.
