---
tags: 1:1
---

Checkin with [[Eliana Herrera]] on March 23, 2023 @ 11:42

## notes
- 

## tagged tasks
```dataviewjs

// any incomplete tasks that are tagged '@eliana'
dv.taskList(
  dv.pages('-"Templates"')
    .file.tasks
    .where(
      t => !t.completed &&
      t.text.includes("@eliana")
  )
);

```

