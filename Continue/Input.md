
> [!Question] What is this site for?
> This is the place to go if you want to add more content to your zettelkasten. Each table presents you with notes you marked with a continue-tag and have at least one unchecked checkbox on it. After a certain number of days (currently set at 30) notes will disappear from these tables. Click on the table titles to access the list without a time-limit. 


## [[Input - Full List Add|Add]] 

> [!note] What appears on this table
> All unprocessed fleeting notes you have taken with Obsidians "daily notes". Our template for daily notes adds **automatically** a cont/in/add tag together with a checkbox. 

```dataview
table hub as "Topic", project as "Project"
FROM #cont/in/add 
And -"Templates"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
AND (date(today) - file.mday).day <30
AND file.name !="Recommended tags, fields and title markers"
```


## [[Input - Full List Extract|Extract]]

> [!NOTE] What appears on this table
> All unprocessed literature notes. Our template for the citations-plugin (if you use Zotero) or the template for manual literature notes adds the cont/in/extract tag **automatically** with a checkbox to all newly created literature notes. It belongs on not fully processed literature-notes, that is literature you have read, maybe taken notes on, but not yet turned into permanent notes. 
```dataview
table up as "Topic", project as "Project"
FROM #cont/in/extract 
AND -"Templates"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
AND (date(today) - file.mday).day <90
AND file.name !="Recommended tags, fields and title markers"
```
## [[Input - Full List Read|Read]]

> [!NOTE] What appears on this table?
All literature notes you have **manually** added a cont/in/read tag together with a checkbox. Add it to literature notes you haven't read the literature yet. As you can see we added this tag to a few notes we hope to be helpful. Check the box and/or delete the tag to remove them from this table. 

```dataview
table hub as "Topic", project as "Project"
FROM #cont/in/read 
AND -"Templates"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
AND (date(today) - file.mday).day <30

```

## [[Input - Full List Readwise]]

> [!NOTE] What appears in this table?
> All Readwise notes with an unchecked checkbox on them (no extra tag needed). With the template we provide Readwise will **automatically** add an unchecked checkbox on every new note it creates or every new batch of highlights it adds to an existing note. Check the box and the note will disappear from this table. 

```dataview
table (date(today) - file.cday).day as "Days old", file.size as "Size", category as "Format", citekey as "Literature Note"
From "Readwise"
WHERE any(file.tasks, (t) => !t.fullyCompleted)
AND (date(today) - file.mday).day <90
sort file.size asc
```







