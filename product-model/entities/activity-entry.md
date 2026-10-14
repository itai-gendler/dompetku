---
domain: settings
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#logActivity
- kind: code
  role: implementation
  target: src/lib/activity.ts
---

# Activity entry

One line of the activity log the owner reads in Settings: what changed, who did it and when.

## Information kept

- **Action** — what happened, such as a transaction created or a sign-in
- **Actor** — the signed-in person; empty for the bot and n8n
- **Detail** — name, amount and currency of what changed
- **Time** — when it happened
