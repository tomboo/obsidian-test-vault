# Obsidian Test Vault

This is a test vault for experimenting with Depot data imports.

## Purpose

- Test importing converted files from Google Drive Depot
- Experiment with Library organization
- Try different Dataview queries
- Learn the import workflow

## Main Vault

The production vault is at: `~/Projects/lexi-writers-studio`

## Depot Integration

Files in `Library/` are imported from the Depot via rclone:

```bash
# Import converted files
rclone copy gdrive:Writing-Archive/unknown/converted \
  /Users/tom/Documents/obsidian-test-vault/Library/unknown/Cleaned \
  --progress
```

## Getting Started

1. Open this folder in Obsidian: **Open folder as vault**
2. Install Dataview plugin: Settings → Community plugins → Dataview
3. Open [[Dashboard]] to see imported files
4. Explore [[Library/]] folder

## Dataview Queries

Try these queries in Dashboard.md (Reading mode):

```dataview
TABLE wordcount, status
FROM "Library"
WHERE wordcount
SORT wordcount DESC
```
