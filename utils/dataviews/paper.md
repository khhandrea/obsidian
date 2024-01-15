---
created-at: "2023-09-21T13:48"
tags:
  - dataview
---
# Paper
```button
name + New paper
type command
action QuickAdd: paper
```

```dataview
TABLE description
FROM #paper
WHERE typeof(annotation-target) = "string"
SORT created-at DESC
```
