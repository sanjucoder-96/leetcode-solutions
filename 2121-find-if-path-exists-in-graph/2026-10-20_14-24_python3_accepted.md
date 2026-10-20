# 2121. Find if Path Exists in Graph
  
<br>**Problem:** https://leetcode.com/problems/find-if-path-exists-in-graph/<br>

**Difficulty:** Easy<br>
**Topics:** Depth-First Search, Breadth-First Search, Union-Find, Graph Theory<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-20 14:24 local time

**Runtime:** 223 ms (beats 91.61389999999999%)
**Memory:** 85.5 MB (beats 79.06939999999997%)


<!-- leetgit:submissionId=2176910242 codeHash=610bf8f75aedbedb2833049b477f09c9a12cbd07913a88b03be6893e222bd322 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def validPath(self, n: int, edges: list[list[int]], source: int, destination: int) -> bool:
        if source==destination:
            return True 
        parent=list(range(n))
        rank=[1]*n

        def find(x):
            if parent[x]!=x:
                parent[x]=find(parent[x])
                return parent[x]
            return x
        def union(x,y):
            a,b=find(x),find(y)
            if a==b:
                return
            if rank[a]>rank[b]:
                parent[b]=a
            elif rank[b]>rank[a]:
                parent[a]=b
            else:
                parent[a]=b
                rank[b]+=1
            
        for u,v in edges:
            union(u,v)
            if find(source)==find(destination): return True
        return False
```
