---
appliesTo:
- {type: capability, id: change-password}
- {type: capability, id: add-family-member}
- {type: capability, id: reset-member-password}
- {type: entity, id: profile}
references:
- kind: code
  role: implementation
  target: src/lib/password.ts#passwordProblems
---

# Passwords have at least 10 characters

A new or temporary password has 10 to 200 characters, no leading or trailing space and is not the username.
