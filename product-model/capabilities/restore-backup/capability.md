---
domain: settings
availability:
- place: web::administration
references:
- kind: code
  role: implementation
  target: src/lib/backup.ts
- kind: code
  role: implementation
  target: src/lib/backup.server.ts#restoreChunk
- kind: code
  role: implementation
  target: src/components/backup-restore.tsx
---

# Restore backup

The owner restores a backup file of at most 20 MB: merging it (rows with the same identity are updated, everything else stays) or replacing everything (all current data is deleted first, after typing GANTI). Sign-in details and integration settings are never taken from the file.
