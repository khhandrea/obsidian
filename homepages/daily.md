---
tags:
  - homepage
---
# Daily
```dataview
CALENDAR date
FROM #daily
WHERE typeof(date) = "date"
```
```dataview
TABLE
	description as "task"
FROM #daily
WHERE typeof(date) = "date"
SORT date DESC
```
