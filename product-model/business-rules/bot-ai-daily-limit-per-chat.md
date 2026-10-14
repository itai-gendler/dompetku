---
appliesTo:
- {type: capability, id: create-transaction-preview}
- {type: entity, id: integration-settings, facts: [Daily AI limit per chat]}
references:
- kind: code
  role: implementation
  target: src/lib/ai-usage.server.ts#botAiQuotaReached
- kind: code
  role: implementation
  target: src/lib/bot.ts#aiTextGate
---

# Bot AI use is capped per chat per day

Messages and photos that need AI count against the chat's daily AI limit (50 by default, 0 for unlimited). Messages without an amount or longer than 300 characters never go to AI.
