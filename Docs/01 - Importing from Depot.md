# Importing Files from Depot

Learn how to pull converted files from the Google Drive Depot into this test vault.

---

## Quick Import (rclone)

### Import from 'unknown' project

```bash
rclone copy gdrive:Writing-Archive/unknown/converted \
  ~/Projects/obsidian-test-vault/Library/unknown/Cleaned \
  --progress
```

### Import from specific project

```bash
# Replace PROJECT_NAME with: you-da-hoe, python, sh-memoir, etc.
rclone copy gdrive:Writing-Archive/PROJECT_NAME/converted \
  ~/Projects/obsidian-test-vault/Library/PROJECT_NAME/Cleaned \
  --progress
```

---

## What Gets Imported

Each file includes:

**YAML Frontmatter:**
- `uid` - Unique identifier (ULID)
- `title` - Original filename (without extension)
- `source_project` - Which project (you-da-hoe, unknown, etc.)
- `wordcount` - Word count
- `status` - Processing status
- `provenance` - Original file metadata

**Markdown Content:**
- Converted from original format (.docx, .rtf, etc.)
- Clean markdown formatting
- Preserves structure and content

---

## After Importing

1. **Refresh Obsidian** - Files should appear in Library folder
2. **Check Dashboard** - Dataview queries will show new files
3. **Browse Library** - Navigate to `Library/PROJECT/Cleaned/`
4. **Verify YAML** - Open file and check frontmatter

---

## Troubleshooting

### Files not appearing

**Check:**
```bash
ls ~/Projects/obsidian-test-vault/Library/unknown/Cleaned/
```

**Should see:** `.md` files with YAML frontmatter

### rclone not configured

```bash
# List configured remotes
rclone listremotes

# Should show: gdrive:
# If not, run: rclone config
```

### Wrong folder structure

Make sure you're copying to:
```
~/Projects/obsidian-test-vault/Library/PROJECT_NAME/Cleaned/
```

NOT:
```
~/Projects/obsidian-test-vault/Library/PROJECT_NAME/converted/
```

---

## Next Steps

- [[02 - Using Dataview]] - Query your imported files
- [[03 - Organizing Files]] - Structure your Library
- [[Dashboard]] - View all imported files

---

**See also:**
- Main vault: `~/Projects/lexi-writers-studio/_System/docs/test-vault-setup-guide.md`
