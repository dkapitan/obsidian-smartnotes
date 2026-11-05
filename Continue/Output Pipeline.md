
> [!question] What is on this page?
> This site helps you to gear your work towards output. The first table lists your project notes with a project/active tag on them - a simple reminder that it is usually best to get a project in the making over the finishing line. 
> The other tables list permanent notes (which are usually more or less developed hubs) you added an  output-tags to, sorted by different stages of development. Use the output-tags to flag out potential project candidates. Remove them when you turn them into actual projects or decide to not follow up on the idea.
> For project management go to [[Projects]]. 

# Projects in the Making (Active)
```dataview
table area as "Area"
FROM #project/active 
sort file.ctime desc
```

# Project Candidates (Ready to Outline)
```dataview
table project as "(Working) Title", area as "Area"
From #output/outline
where file.name =![[Recommended tags, fields, and title markers]]
sort area asc
```
# Project Candidates (in Development)
```dataview
table project as "(Working) Title", area as "Area"
From #output/develop
where file.name =![[Recommended tags, fields, and title markers]]
sort area asc
```
# Project Candidates (early ideas)
```dataview
table project as "(Working) Title", area as "Area"
From #output/idea
where file.name =![[Recommended tags, fields, and title markers]]
sort area asc
```
