---
appliesTo:
- {type: context, context: {place: automation-api}}
- {type: entity, id: integration-settings}
references:
- kind: code
  role: implementation
  target: src/lib/api-key.server.ts#checkApiKey
---

# The automation API requires the n8n API key

Every automation endpoint answers only a request carrying the n8n API key; with no key of at least 24 characters configured, every request is refused.
