---
tags: 1:1
---

Checkin with [[Eliana Herrera]] on March 22, 2023 @ 15:27

## notes
- [ ] #task testing 1 2 3 @postlight

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

