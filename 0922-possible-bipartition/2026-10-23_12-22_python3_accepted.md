# 922. Possible Bipartition
  
<br>**Problem:** https://leetcode.com/problems/possible-bipartition/<br>

**Difficulty:** Medium<br>
**Topics:** Depth-First Search, Breadth-First Search, Union-Find, Graph Theory, Graph Coloring, Bipartite Graph<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-23 12:22 local time

**Runtime:** 25 ms (beats 74.31319999999997%)
**Memory:** 23.7 MB (beats 46.634599999999985%)


<!-- leetgit:submissionId=2179436200 codeHash=eb6b0793c8a3ce36ecc539e42e1628db58e2c1c46cdffd6a9889f2554ef7e509 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from collections import deque
class Solution:
    def possibleBipartition(self, n: int, dislikes: list[list[int]]) -> bool:
        adj= [[] for _ in range(n+1)]
        for u,v in dislikes:
            adj[u].append(v)
            adj[v].append(u)
        def check(adj,src,color)->bool:
            dq=deque()
            
            # print(color)
            color[src]=1
            dq.append(src)
            while dq:
                front=dq.popleft()
                
                for v in adj[front]:
                    if color[v]==color[front]:
                        return False
                    elif color[v]==-1:
                        color[v]=1-color[front]
                        dq.append(v)
            return True
        color=[-1]*(n+1)
        for i in range(n+1):
            if color[i]==-1:
                if not check(adj,i,color): return False
        return True
                
        
```
