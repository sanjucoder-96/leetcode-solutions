# 1692. Number of Ways to Reorder Array to Get Same BST
  
<br>**Problem:** https://leetcode.com/problems/number-of-ways-to-reorder-array-to-get-same-bst/<br>

**Difficulty:** Hard<br>
**Topics:** Array, Math, Divide and Conquer, Dynamic Programming, Tree, Union-Find, Binary Search Tree, Memoization, Combinatorics, Binary Tree, Fermat's Little Theorem<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-18 20:52 local time

**Runtime:** 39 ms (beats 65.03049999999996%)
**Memory:** 23.8 MB (beats 76.68699999999998%)


<!-- leetgit:submissionId=2175498044 codeHash=0c4dbb86ce6e1d065e196bb5c63cbd600c5cbfcb24a5ae2394c450843b52d778 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from math import comb
class Solution:
    def numOfWays(self, nums: list[int]) -> int:
        MOD=int(1e9+7)
        def solve(nums):
            if(len(nums)<3):
                return 1
            root=nums[0]
            left=[x for x in nums if x<root]
            right=[x for x in nums if x>root]
            z=comb(len(nums)-1,len(left))
            return (((z*solve(left))%MOD)*solve(right))%MOD
        return (solve(nums)-1)%MOD
```
