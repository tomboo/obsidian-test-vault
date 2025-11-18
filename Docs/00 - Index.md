# Test Vault Documentation

This is a simplified version of the main vault's documentation, focused on testing Depot imports.

---

## Quick Links

### Getting Started
- [[01 - Importing from Depot]] - How to pull files from the Depot
- [[02 - Using Dataview]] - Query imported files
- [[03 - Organizing Files]] - Structure your Library

### Reference
- Main Vault Docs: `~/Projects/lexi-writers-studio/Docs/`
- Depot Pipeline Docs: `~/Projects/lexi-writers-studio/_System/docs/`

---

## Test Vault Purpose

This vault is for **experimentation only**. Use it to:

1. **Test imports** - Pull converted files from Depot
2. **Try Dataview queries** - Practice querying YAML frontmatter
3. **Experiment with structure** - Try different organization approaches
4. **Learn workflows** - Practice before using main vault

**Safe to delete and recreate anytime!**

---

## Imported Files

Currently in Library:
- `Library/unknown/Cleaned/` - 6 test files from Depot

To import more:
```bash
rclone copy gdrive:Writing-Archive/PROJECT/converted \\
  ~/Projects/obsidian-test-vault/Library/PROJECT/Cleaned
```

---

## Next Steps

1. Install Dataview plugin (if not already)
2. Open [[Dashboard]] to see imported files
3. Try editing YAML frontmatter
4. Create links between Library and Projects
5. Experiment with different queries

---

**Last Updated:** 2025-11-18
