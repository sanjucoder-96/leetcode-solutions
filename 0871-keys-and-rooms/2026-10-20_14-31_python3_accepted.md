# 871. Keys and Rooms
  
<br>**Problem:** https://leetcode.com/problems/keys-and-rooms/<br>

**Difficulty:** Medium<br>
**Topics:** Depth-First Search, Breadth-First Search, Graph Theory<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-20 14:31 local time

**Runtime:** 1 ms (beats 31.540800000000004%)
**Memory:** 19.5 MB (beats 95.1618%)


<!-- leetgit:submissionId=2176914077 codeHash=737c80dba2da2d4e43861ad063c6d0f3a3ccc9e3c2f9ba165c8312ebc03f4f3d notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def canVisitAllRooms(self, rooms: list[list[int]]) -> bool:
        n=len(rooms)
        
        dq=deque()
        visited=[False]*n
        visited[0]=True
        dq.append(0)
        while dq: 
            front=dq.popleft()
            for v in rooms[front]:
                if not visited[v]:
                    visited[v]=True
                    dq.append(v)
        return sum(1 for i in visited if i)==n
```
