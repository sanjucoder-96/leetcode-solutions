# 2121. Find if Path Exists in Graph
  
<br>**Problem:** https://leetcode.com/problems/find-if-path-exists-in-graph/<br>

**Difficulty:** Easy<br>
**Topics:** Depth-First Search, Breadth-First Search, Union-Find, Graph Theory<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-20 14:15 local time

**Runtime:** 378 ms (beats 51.94719999999997%)
**Memory:** 83.3 MB (beats 93.58909999999997%)


<!-- leetgit:submissionId=2176904534 codeHash=e0107051866b759e8f6d38fb8d2a092219563ad36549e6be81749c7a5e82a68f notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from collections import deque

class Solution:
    def validPath(self, n: int, edges: list[list[int]], source: int, destination: int) -> bool:
        visited=[False]*(n)
        dq=deque()
        adj=[[] for _ in range(n) ]
        for l in edges:
            u,v=l[0],l[1]
            adj[u].append(v)
            adj[v].append(u)
        print(adj)
        dq.append(source)
        visited[source]=True
        while dq:
            front=dq.popleft()
            if front==destination:
                return True
            
            for v in adj[front]:
                if not visited[v]:
                    dq.append(v)
                    visited[v]=True

        return False
        
```
