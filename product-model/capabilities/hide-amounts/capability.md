---
availability:
- place: web::app
references:
- kind: code
  role: implementation
  target: src/lib/privacy.ts
- kind: code
  role: implementation
  target: src/components/app-shell.tsx
---

# Hide amounts

Turn privacy mode on for this device, with the eye button or Shift+H: every amount, balance, chart value and gold weight is hidden; percentages and counts stay. Exports and the bot are not affected.
