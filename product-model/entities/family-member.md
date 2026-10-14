---
kind: person
acts: external
domain: settings
relations:
- {entity: profile, verb: signs in as, cardinality: one-to-one}
- {entity: wallet-access, verb: holds, cardinality: one-to-many}
references:
- kind: code
  role: implementation
  target: src/lib/users.server.ts#createMember
- kind: code
  role: implementation
  target: src/lib/permissions.ts#MEMBER_MODULES
---

# Family member

A person the owner adds in Settings → Users. A family member signs in with their own password, opens only the dashboard, transactions, accounts, reports and their profile, and sees or changes only the accounts the owner shares with them.

## Information kept

- **Must change password** — set when the owner gives a temporary password; cleared when the member chooses their own

## States

### Active

The member can sign in.

### Inactive

The owner switched the member off; every session ends and sign-in is refused.
