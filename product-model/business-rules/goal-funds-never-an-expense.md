---
appliesTo:
- {type: capability, id: add-goal-funds}
- {type: capability, id: withdraw-goal-funds}
- {type: entity, id: goal}
references:
- kind: code
  role: implementation
  target: src/lib/goals.ts#planGoalFunds
---

# Goal funds never record an expense

Adding or withdrawing goal funds records at most a transfer between the chosen account and the goal's savings account, so net worth is unchanged.
