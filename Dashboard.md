# Test Vault Dashboard

Welcome to your test vault for experimenting with Depot imports.

## Active Project

[[Projects/TestNovel/Manuscript/]]

## Library

[[Library/]] - Imported files from Depot

## Quick Stats

```dataview
TABLE wordcount, status, source_project
FROM "Library"
WHERE type = "scene"
SORT file.name
LIMIT 10
```

## All Imported Files

```dataview
LIST
FROM "Library"
SORT file.mtime DESC
```
