---
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#saveProfile
- kind: code
  role: implementation
  target: src/lib/profile.ts
---

# Profile

The sign-in identity and personal details of the owner or a family member.

## Information kept

- **Username** — the sign-in name; a member's is lower-case and never changes after creation
- **Display name** — the name shown instead of the username when set
- **Address** — an optional postal address
- **Profile photo** — an optional small picture
- **Password** — the secret used to sign in; for the owner a password chosen in the app replaces the configured one
