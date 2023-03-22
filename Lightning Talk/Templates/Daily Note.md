---
creation date: <% tp.file.creation_date() %>
tags: DailyNote <% tp.date.now("Y") %>
summary:
---
**[[<% tp.date.now("YYYY-MM-DD ddd", -1) %>|< Day before]] | [[<% tp.date.now("YYYY-MM-DD ddd", 1) %>|Next day >]]**

## inspiration
<% tp.web.daily_quote() %>

## weather
<% tp.user.weather() %>

## notes
- 

## daily check list
### morning
- [ ] fill out [[<% tp.date.now("YYYY-MM-DD ddd", -1) %>|yesterday]]'s summary
- [ ] check email
- [ ] check [[Reports]]
### evening
- [ ] clean unused headings in Daily Note
- [ ] check tomorrow's calendar
- [ ] fill out today's summary

## self checkin
### how are you feeling? 
- 
### what are you grateful for? 
- 
### what's on your mind?
- 
### anything to report from last night?
- 

## tasks
### over due
```tasks
not done
due before <% tp.date.now("YYYY-MM-DD") %>
short mode
```

### due today
```tasks
not done
due on <% tp.date.now("YYYY-MM-DD") %>
short mode
```

### done today
```tasks
done on <% tp.date.now("YYYY-MM-DD") %>
short mode
```

## meetings
```dataview
LIST from "Postlight/Projects"
WHERE file.ctime.day = date({{date:YYYY-MM-DD}}).day
AND file.ctime.month = date({{date:YYYY-MM-DD}}).month
AND file.ctime.year = date({{date:YYYY-MM-DD}}).year
AND contains(tags, "meeting")
```

## checkins
```dataview
LIST from "Postlight/Staff"
WHERE file.ctime.day = date({{date:YYYY-MM-DD}}).day
AND file.ctime.month = date({{date:YYYY-MM-DD}}).month
AND file.ctime.year = date({{date:YYYY-MM-DD}}).year
AND contains(tags, "1:1")
```

## interviews
```dataview
LIST from "Postlight/Interviews"
WHERE file.ctime.day = date({{date:YYYY-MM-DD}}).day
AND file.ctime.month = date({{date:YYYY-MM-DD}}).month
AND file.ctime.year = date({{date:YYYY-MM-DD}}).year
AND contains(tags, "interview")
```

## music
- 
#music

## edited today
```dataview
LIST FROM ""
WHERE file.mtime.day = date({{date:YYYY-MM-DD}}).day 
AND file.name != this.file.name
AND file.mtime.month = date({{date:YYYY-MM-DD}}).month 
AND file.mtime.year = date({{date:YYYY-MM-DD}}).year
AND !contains(tags, "meeting")
AND !contains(tags, "interview")
AND !contains(tags, "1:1")
```

