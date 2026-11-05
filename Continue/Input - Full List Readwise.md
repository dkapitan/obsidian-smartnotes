```dataview
table (date(today) - file.cday).day as "Days old", file.size as "Size", category as "Format", citekey as "Literature Note"
From "Readwise"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
sort file.size asc
```

