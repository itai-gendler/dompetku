---
relations:
- {entity: transaction, verb: is saved as, cardinality: one-to-one}
references:
- kind: code
  role: implementation
  target: src/lib/bot.server.ts#handleBotUpdate
- kind: code
  role: implementation
  target: supabase/schema.sql
---

# Transaction preview

A Pratinjau: the transaction the bot read from one chat message or receipt photo, waiting in that chat for Save or Cancel. It keeps how it was read and, for a receipt, the photo.

## Information kept

- **Chat** — the Telegram chat the message came from
- **Kind** — income or expense
- **Amount** — the amount read
- **Currency** — IDR or USD
- **Category** — an existing category name, or none
- **Account** — an existing account name; without one the bot's default account is used on save
- **Date** — the day of the transaction
- **Description** — up to 200 characters
- **Merchant** — the merchant read from a receipt
- **Receipt items** — up to 50 item lines read from a receipt
- **Pocket tag** — the #tag given in the message
- **Read by** — quick parse without AI, AI, or receipt OCR
- **Receipt photo** — the photo, kept privately while the preview waits
- **Awaiting description** — set for up to 10 minutes after Keterangan is tapped, so the next chat message becomes the description

## States

### Proposed

Waiting in the chat for Save or Cancel.

### Accepted

Saved as a transaction.

### Dismissed

Cancelled, or expired after 48 hours; nothing was saved.

### Undone

Its transaction was removed again with Undo.
