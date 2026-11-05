---
aliases:
  - "100"
---

## Curated Overview over Entry Notes

## [[SRDP]]
## [[Data stations as the cornerstone for federated health data infrastructure]]

## Seminal papers



---
## Related Projects
#### Active Projects
[[Writing a book with Cobus]]
#### Project Ideas
...

----
```dataview
TABLE WITHOUT ID
 file.link as "Hubs not listed above", 
length(file.inlinks) as "Inlinks", length(file.outlinks) as "Outlinks"
from #hub 
AND -outgoing([[100 Area of Interest]])
where contains(area, 100)
SORT length(file.inlinks) asc
```



