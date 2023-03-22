

## active projects
```tasks
not done
description includes postlight
sort by priority
```

## past due
```tasks
not done
due before date(today)
```

## due today
```tasks
not done
due today
```

## due this week
```tasks
not done
happens after last sunday
happens before this saturday
```

## due in the next 7 days
```tasks
not done
due before in 7 days
hide task count
```

## no due date
```tasks
not done
no due date
```

## recurring
```tasks
not done
is recurring
group by due
hide task count
```

## other tasks
```dataviewjs

dv.taskList(
  dv.pages('-"Templates"')
  .file.tasks
  .where(t => !t.completed && 
    !t.text.includes("@adrienne") && 
    !t.text.includes("@austin") && 
    !t.text.includes("@brian") && 
    !t.text.includes("@frankie") && 
    !t.text.includes("@jae") && 
    !t.text.includes("@johnny") && 
    !t.text.includes("@matt") && 
    !t.text.includes("@jordan") && 
    !t.text.includes("@aaron") && 
    !t.text.includes("@russ") && 
    !t.text.includes("#task")
  )
)

```
