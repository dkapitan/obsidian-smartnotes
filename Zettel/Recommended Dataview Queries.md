project::[[Getting Started]]
- [ ] #cont/in/read 

> [!Info] Recommended external ressources
> A good introduction to Dataview and a comprehensive overview over its functions can be found here: https://obsidian.rocks/dataview-in-obsidian-a-beginners-guide/
> 
> A cheat sheet over the commands for copy and paste with simple descriptions on how to alter them to your needs: https://github.com/seburbandev/obsidian-dataview-cheatsheet

Here we explain briefly what you need to do to adjust the recommended codes within the starter-kit. 

Remember: Any code in Obsidian sits between two lines of three backticks each. Without further instructions any text between these lines can be easily copied (like in the examples below). For Dataview you need to add the word dataview on the first line:
![[Pasted image 20240530120829.png]]
To use our examples below simply copy the text and add it between these two lines. 

# Templates and use cases:
## 1. Simple Lists
```
list 
from #person 
sort asc
```
#### Function 
This Dataview template lists all notes with a specific tag (here: #person) and sorts them in alphabetical ascending order. 
#### Use Case
Use this query for lists of all sorts. We already have the index with names (this one) or the index with terms (with the index-tag #index). 
You can come up with all kinds of lists. Simply invent a fitting tag you add on selected notes. Maybe for exceptionally insightful literature (on literature notes)? Or breakthrough ideas (on daily notes)? Or fundamental questions (on permanent notes)?
## 2. Tables

#### Function
Tables are great to give ourselves an overview over the different possibilities to advance our work. You'll find many examples in the continue folder. 

#### Use case
A typical example would be [[Input#Input - Full List Add Add|the table]] that gives us an overview over all unprocessed fleeting notes that are not older than 30 days. As we treat "daily notes" as fleeting notes, they automatically have a "cont/in/add"-tag on them and an unchecked checkbox. 
Here is the little Dataview query: 
```
table hub as "Topic", project as "Project"
FROM #cont/in/add 
WHERE any(file.tasks, (t) => !t.fullyCompleted)
AND (date(today) - file.mday).day <30
```
#### Explanation
TABLE creates the table with the first column for the filename (per default), followed by what is specified for the variables listed (that is here hub and project). The titles of the column are here modified by "as" with the title followed in quotation marks (here "Topic" for hub and "Project" for project). In order for Dataview to read the variable we need to use the double colons "::" on the respective notes. That is here "hub::" and "project::" followed by either plain text or a link. 
FROM specifies to list only those notes with the cont/in/add tag on them.
WHERE any(file.tasks, (t) => !t.fullyCompleted) makes sure we only have notes with at least one unchecked checkbox on them. 
AND (date(today) - file.mday).day <30 removes all notes older than 30 days. 
#### Guide
1. You can change the grace period by simply changing 30 to another number. 
2. You can simply exchange, remove or add more columns by adding more variables separated by comma into the first line. You do not have to change the title with "as". 
3. You can simply specify another tag (or folder).
4. Please consult the [[Recommended Dataview Queries#^48c0aa|external resources]] for further information. 

## 3. [[Template dataview incoming links not listed]]

```
LIST
FROM [[CURRENT NOTE]]  AND -outgoing([[CURRENT NOTE]])
SORT file.name ASC
```
#### Function
This Dataview template lists all notes that are pointing to the current note except for those which are explicitly also linked to from this note.
#### Use case
This template allows you to add notes to hubs with curated links without having to interrupt your work flow by just linking forward to them. This makes most sense for higher order hubs, like MOC's where you point to other hubs. If you link to this MOC it will appear there on this list. Later, when you work on this MOC, you see all added notes that are not yet listed on the main body of that page. As soon as you add manually a link note it will disappear from the automatically generated list. 
#### Guide
1. Copy the dataview query or add the [[Template dataview Incoming links not listed|template]] from the menu (Ctrl+P)
2. Replace "CURRENT NOTE" with the actual name of the note with the curated list of links.
#### Explanation
LIST is the command to simply list all notes
FROM specifies to list only those linking to the note within the round brackets. 
AND -outgoing excludes (that is what the minus-sign is for) those linked to (outgoing) from this note. 
SORT filme.name ASC sorts the files by name in ascending order. 

## 4. Excluding certain files or folders
In the code for the tables for [[Input]] you'll find two additional lines not mentioned above. 
```
AND -"Templates"
```
This line removes all notes within the folder "Templates" (because we don't want our templates and cheat sheets to appear in all tables). It has to be underneath the line starting with "FROM".
```
AND file.name !="Recommended tags, fields and title markers"
```
This line removes the note called "Recommended tags, fields and title markers" (because we don't want it to appear on all tables). It has to be underneath the line starting with "WHERE". 
Simply replace the folder- or file-name within the parentheses to exclude folders or files of your choice. 