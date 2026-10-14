---
appliesTo:
- {type: capability, id: restore-backup}
- {type: entity, id: transaction, effect: removes}
references:
- kind: code
  role: implementation
  target: src/lib/backup.ts#REPLACE_CONFIRM_WORD
---

# Replacing all data needs the word GANTI

A restore that deletes the current data first runs only after the owner types GANTI; a merge never deletes anything.
