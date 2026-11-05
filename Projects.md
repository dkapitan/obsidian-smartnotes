
> [!NOTE] What is this page?
> This is the page with an overview over your projects. The tables are created by dataview and simply list all pages with the respective project tags: project/active, project/someday, project/idea, and project/finished plus the area specified on the project note.

#### Active Projects
```dataview
table area 
from #project/active 
where file.name !="Recommended tags, fields and title markers"
sort asc
```
#### Idle Projects
```dataview
table area
from #project/idle  
where file.name !="Recommended tags, fields and title markers"
sort asc
```
#### Finished Projects
```dataview
table area
from #project/finished  
where file.name !="Recommended tags, fields and title markers"
sort asc
```

> [!Tip] Customize it!
>It is likely that you want to give yourself a different kind of project overview and manually sort them for different criteria (for example by importance, urgency or duration). Use the [[Template dataview incoming links not listed]] to make sure you keep track of all projects. 
