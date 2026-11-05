```dataview
table topic as "Topic", project as "Project", (date(today) - file.cday).day as "Days old", (date(today) - file.mday).day as "Days untouched"
FROM #cont/in/add  
AND -"Templates"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
```
