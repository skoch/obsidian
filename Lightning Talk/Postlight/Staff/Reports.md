## direct reports
```dataview
TABLE WITHOUT ID
  link(file.link, aliases[0]) AS Report,
  pronouns, 
  startdate as "start date", 
  location,
  birthday,
  title
FROM "Postlight/Staff"
WHERE title
AND contains(tags, "report")
AND !contains(tags, "z_old")
SORT file.name
```

## staff
```dataview
TABLE WITHOUT ID
  link(file.link, aliases[0]) AS Staff,
  pronouns,
  startdate as "start date", 
  location,
  birthday,
  title
FROM "Postlight/Staff"
WHERE title
AND !contains(tags, "report")
AND !contains(tags, "z_old")
SORT file.name
```

## z_old
```dataview
TABLE WITHOUT ID
link(file.link, aliases[0]) AS Staff,
pronouns as Pronouns, 
startdate as "Start Date", 
location as Location, 
birthday as Birthday, 
title as Title
FROM "Postlight/Staff"
WHERE title
AND contains(tags, "z_old")
SORT file.name
```
