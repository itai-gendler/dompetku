---
appliesTo:
- {type: entity, id: profile, effect: changes, facts: [Display name, Password]}
permits:
- actors: [owner]
- related:
  - {verb: signs in as, entity: family-member}
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#changePassword
---

# Who changes a name or password

Each person changes their own display name and password; the owner also renames family members and gives them temporary passwords.
