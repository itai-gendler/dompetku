---
domain: goals
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/goals.ts#planGoalFunds
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#addGoalFunds
---

# Add goal funds

The owner puts money towards a goal. When the goal has a savings account and another account is chosen, the money moves as a transfer into the savings account; otherwise only the saved amount changes. It never records an expense.
