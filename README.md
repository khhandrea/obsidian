
# Obsidian
todo
- Plugins 정리
- Properties 정리
- Tags 정리

| Directory  | Description                                  |
| ---------- | -------------------------------------------- |
| tempaltes  | Markdown templates                           |
| playground | Test for obsidian features and markdown etc. |
| daily      | Directory for daily notes                    |
| papers     | Archiving papers                             |
| study      | Studying on papers, informations etc.        |
| note       | Memoization                                  | 

```dataview
TABLE annotation-target AS "url"
FROM #paper
WHERE typeof(annotation-target) = "string"
```

```dataview
CALENDAR date
FROM #daily
WHERE typeof(date) = "date"
```
