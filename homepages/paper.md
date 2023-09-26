---
created-at: "2023-09-21T13:48"
tags:
  - homepage
---
# Paper
```button
name New paper
type command
action QuickAdd: paper
```

```dataview
TABLE annotation-target AS "url"
FROM #paper
WHERE typeof(annotation-target) = "string"
```
