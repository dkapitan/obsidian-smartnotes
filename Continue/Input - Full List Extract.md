```dataview
table hub as "Topic", project as "Project", (date(today) - file.cday).day as "days old", (date(today) - file.mday).day as "days untouched"
FROM #cont/in/extract 
WHERE any(file.tasks, (t) => !t.fullyCompleted)
```
