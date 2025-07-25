---
id: stroke-to-path-bug
aliases: []
tags: []
---

When doing stroke-to-path generally you shape gets busted

to fix this:

1. path > reverse
2. path > stroke-to-path

fixed


### text inside or outside path
pd: path > reverse also works for chosing where the text goes relative to a path, inside or outside
