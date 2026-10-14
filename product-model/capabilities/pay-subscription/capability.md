---
availability:
- place: web::app
- place: telegram-bot
references:
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#paySubscription
- kind: code
  role: implementation
  target: src/lib/finance.server.ts#botCommand
---

# Pay subscription

Record a subscription's bill as paid: an expense of the price plus tax in its category (Langganan when none) from its account, and the next bill moved on by its interval. Reached from Subscriptions, Reminders and the bot's /bayar, which records at once without a preview.
