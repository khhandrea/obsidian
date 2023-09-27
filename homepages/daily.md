---
created-at: 2023-09-20T12:00:00
tags:
  - homepage
---
# Daily
```dataview
CALENDAR date
FROM #daily
WHERE typeof(date) = "date"
```
---
```dataview
TABLE description, done
FROM #daily
WHERE typeof(date) = "date"
SORT date DESC
```
