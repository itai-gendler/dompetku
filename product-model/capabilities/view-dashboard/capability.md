---
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeDashboard
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#computeMemberDashboard
---

# View dashboard

See a month at a glance. The owner's dashboard counts every account plus gold and receivables in net worth and lists bills of the next 14 days; a family member's covers only their accounts.
