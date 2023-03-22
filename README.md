# Obsidian

## How I Organize My Brain

Everything centers around the Daily Note. Hotkeys are used to create files for tasks that happen regularly and queries in the Daily Note link everything that's important for that day.

I track projects, people, tasks, meetings, interviews. Everything is linked back to the day it happened.

I also use this for some light journaling as well as a way to prepare for my day by answering a few general questions as I start my day and when I end my day.

## Plugins

- [Dataview](https://github.com/blacksmithgu/obsidian-dataview)
  - used to query your notes like a database
```dataview
LIST from "Postlight/Projects"
WHERE file.ctime.day = date(2023-03-22).day
AND file.ctime.month = date(2023-03-22).month
AND file.ctime.year = date(2023-03-22).year
AND contains(tags, "meeting")
```
- [Periodic Notes](https://github.com/liamcain/obsidian-periodic-notes)
  - expands on the idea of daily notes and introduces weekly and monthly notes
  - organizes notes based on your preferences
  - eg: `YYYY/MM/YYYY-MM-DD ddd` for your daily note
- [Tasks](https://github.com/obsidian-tasks-group/obsidian-tasks)
  - track (and query!) tasks across your entire vault
  - [Docs](https://obsidian-tasks-group.github.io/obsidian-tasks/)
- [Templater](https://github.com/SilentVoid13/Templater)
  - create template files / snippets that can be used in various ways
  - [Docs](https://silentvoid13.github.io/Templater/)
