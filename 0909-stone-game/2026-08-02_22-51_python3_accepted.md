# 909. Stone Game
  
<br>**Problem:** https://leetcode.com/problems/stone-game/<br>

**Difficulty:** Medium<br>
**Topics:** Array, Math, Dynamic Programming, Game Theory<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-08-02 22:51 local time

**Runtime:** 236 ms (beats 32.6905%)
**Memory:** 43.1 MB (beats 30.582600000000028%)


<!-- leetgit:submissionId=2091684215 codeHash=b2c71a34a30cbca44c318dbdfb0dac99873a1628d4126a78044c630b622ec22f notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def stoneGame(self, piles: List[int]) -> bool:
        n=len(piles)

        dp=[[-1]*n for _ in range(n)]

        def solve(i,j):
            if i>j:
                return 0
            if dp[i][j]!=-1: return dp[i][j]

            take_i=piles[i]+min(solve(i+2,j),solve(i+1,j-1))
            take_j=piles[j]+min(solve(i,j-2),solve(i+1,j-1))

            dp[i][j]=max(take_i,take_j)
            return dp[i][j]

        s=sum(piles)
        res=solve(0,len(piles)-1)
        return res>s/2
```
