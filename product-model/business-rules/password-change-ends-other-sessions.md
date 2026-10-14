---
appliesTo:
- {type: capability, id: change-password}
- {type: capability, id: reset-member-password}
- {type: capability, id: deactivate-family-member}
- {type: entity, id: profile}
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#changePassword
---

# A new password ends every other session

Changing a password ends every other session of that person at once; resetting or deactivating a member ends all of theirs.
