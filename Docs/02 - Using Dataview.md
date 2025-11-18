# Using Dataview with Imported Files

Learn how to query imported files using Dataview plugin.

---

## Install Dataview

1. Settings → Community plugins
2. Turn off Safe Mode
3. Browse → Search "Dataview"
4. Install → Enable

---

## Basic Queries

### List all imported files

```dataview
LIST
FROM "Library"
SORT file.name
```

### Show files with wordcount

```dataview
TABLE wordcount, status
FROM "Library"
WHERE wordcount
SORT wordcount DESC
```

### Files by project

```dataview
TABLE wordcount, status, source_project
FROM "Library"
GROUP BY source_project
```

---

## Filtering

### Only raw files

```dataview
TABLE wordcount, status
FROM "Library"
WHERE status = "raw"
```

### Files with tags

```dataview
TABLE tags, wordcount
FROM "Library"
WHERE tags
```

### High wordcount files

```dataview
TABLE wordcount, status
FROM "Library"
WHERE wordcount > 500
SORT wordcount DESC
```

---

## Advanced Queries

### Total wordcount by project

```dataview
TABLE sum(rows.wordcount) as "Total Words"
FROM "Library"
WHERE wordcount
GROUP BY source_project
```

### Files modified recently

```dataview
TABLE file.mtime as "Modified", wordcount
FROM "Library"
SORT file.mtime DESC
LIMIT 10
```

### Check for required fields

```dataview
TABLE uid, source_project
FROM "Library"
WHERE !uid
```

---

## Using in Dashboard

Add queries to `Dashboard.md`:

1. Open Dashboard.md in **Edit mode**
2. Add a Dataview code block
3. Switch to **Reading mode** to see results

Example:
````markdown
## My Files

```dataview
TABLE wordcount, status
FROM "Library"
SORT file.name
```
````

---

## Troubleshooting

### Query not rendering

**Fix:** Make sure Dataview plugin is installed and enabled

### No results

**Check:**
1. Files are in `Library/` folder
2. Files have YAML frontmatter
3. Field names match (case-sensitive)

### Syntax errors

- Close all code blocks with ` ``` `
- Use correct field names: `wordcount` not `word_count`
- Use quotes for string values: `WHERE status = "raw"`

---

## Learn More

- Dataview documentation: https://blacksmithgu.github.io/obsidian-dataview/
- Main vault queries: `Dashboard.md` in main vault

---

**Next:** [[03 - Organizing Files]]
