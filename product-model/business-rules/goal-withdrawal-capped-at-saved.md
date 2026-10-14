---
appliesTo:
- {type: capability, id: withdraw-goal-funds}
- {type: entity, id: goal, facts: [Saved amount]}
references:
- kind: code
  role: implementation
  target: src/lib/goals.ts#planGoalFunds
---

# A goal withdrawal is capped at what is saved

Withdrawing more than the saved amount withdraws only the saved amount.
