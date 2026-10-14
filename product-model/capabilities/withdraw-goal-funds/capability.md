---
domain: goals
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/goals.ts#planGoalFunds
---

# Withdraw goal funds

The owner takes money out of a goal, at most what is saved. With a savings account and another account chosen, it moves as a transfer out of the savings account.
