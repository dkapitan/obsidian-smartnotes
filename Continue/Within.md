# Sort / Split
```dataview
table up as "Parent", file.size as "Size"
from #cont/zk/sort 
where file.name =![[Recommended tags, fields, and title markers]]
SORT file.size ASC
```
# Connect 
```dataview
table up as "Parent", length(file.outlinks) as "Out", length(file.inlinks) as "In"
from #cont/zk/connect
where file.name =![[Recommended tags, fields, and title markers]]
SORT file.mday DESC
```
# Elaborate / Differentiate 
```dataview
table up as Parent, (date(today) - file.mday).day as "untouched" 
from #cont/zk/differentiate 
where file.name =![[Recommended tags, fields, and title markers]]
SORT file.mday DESC
```
# Proceed
```dataview
table up as Parent, (date(today) - file.mday).day as "untouched" 
from #cont/zk/proceed 
where file.name =![[Recommended tags, fields, and title markers]]
SORT file.mday DESC
```

