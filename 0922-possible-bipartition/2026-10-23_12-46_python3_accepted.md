# 922. Possible Bipartition
  
<br>**Problem:** https://leetcode.com/problems/possible-bipartition/<br>

**Difficulty:** Medium<br>
**Topics:** Depth-First Search, Breadth-First Search, Union-Find, Graph Theory, Graph Coloring, Bipartite Graph<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-23 12:46 local time

**Runtime:** 141 ms (beats 5.08199999999997%)
**Memory:** 23.8 MB (beats 46.634599999999985%)


<!-- leetgit:submissionId=2179452829 codeHash=456c7b13dd34da205a7dcb6ba52772ebb1047f55bc852995ca180c4d3ae42936 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    class DSU:
        def __init__(self,size):
            self.parent=list(range(size))
            self.rank=[0]*size
        def find(self,v):
            if self.parent[v]==v: return v
            self.parent[v]=self.find(self.parent[v])
            return self.parent[v]
        def union(self,x,y):
            a,b=self.find(x),self.find(y)
            if a==b: return
            if self.rank[a]>self.rank[b]:
                self.parent[b]=a
            elif self.rank[b]>self.rank[a]:
                self.parent[a]=b
            else:
                self.parent[a]=b
                self.rank[b]+=1
        

    def possibleBipartition(self, n: int, dislikes: list[list[int]]) -> bool:
        adj=[[] for _ in range(n+1)]
        for u,v in dislikes:
            adj[u].append(v)
            adj[v].append(u)
        ds=self.DSU(2*n+1)
        for i in range(1,n+1):
            for v in adj[i]:
                if ds.find(v)==ds.find(i):
                    return False
                ds.union(i,v+n)
                ds.union(v,i+n)
        return True

```
