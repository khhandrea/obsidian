---
created-at: 2023-09-20T12:00:00
tags:
  - dataview
---
# Daily

```dataview
CALENDAR date
FROM #daily
WHERE typeof(date) = "date"
```

```dataview
TABLE done
FROM #daily
WHERE typeof(date) = "date"
SORT date DESC
```
