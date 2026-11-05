```dataview
table (date(today) - file.cday).day as "age", hub as "Topic", project as "Project", file.etags as "Tasks"
from #cont 
OR #output/outline
AND -"Templates"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
AND file.name !="Recommended tags, fields and title markers"
Sort file.cday asc
```
