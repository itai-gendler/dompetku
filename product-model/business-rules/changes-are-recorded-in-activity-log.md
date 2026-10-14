---
appliesTo:
- {type: capability, id: record-transaction}
- {type: capability, id: edit-transaction}
- {type: capability, id: delete-transaction}
- {type: capability, id: create-account}
- {type: capability, id: edit-account}
- {type: capability, id: delete-account}
- {type: capability, id: pay-subscription}
- {type: capability, id: pay-installment}
- {type: capability, id: add-goal-funds}
- {type: capability, id: withdraw-goal-funds}
- {type: capability, id: record-recurring-transaction}
- {type: capability, id: add-family-member}
- {type: capability, id: sign-in}
- {type: capability, id: sign-out}
- {type: capability, id: undo-bot-transaction}
- {type: entity, id: activity-entry}
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#logActivity
---

# Every change to the data is recorded in the activity log

Creating, changing and deleting data, payments, sign-ins, sign-outs and bot commands each add an activity entry with who acted (empty for the bot and n8n), what changed and when.
