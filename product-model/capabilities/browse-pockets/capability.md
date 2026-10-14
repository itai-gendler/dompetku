---
domain: accounts
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/pockets.server.ts#pocketsBotText
- kind: code
  role: implementation
  target: src/lib/pockets.ts
---

# Browse pockets

See each pocket's remaining amount this month and whether it is low or empty.
