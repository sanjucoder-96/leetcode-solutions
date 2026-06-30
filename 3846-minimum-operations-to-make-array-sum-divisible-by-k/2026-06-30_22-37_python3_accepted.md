# 3846. Minimum Operations to Make Array Sum Divisible by K
  
<br>**Problem:** https://leetcode.com/problems/minimum-operations-to-make-array-sum-divisible-by-k/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Math<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-30 22:37 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.1 MB (beats 95.9958%)


<!-- leetgit:submissionId=2051482264 codeHash=d3beffc4b7f75f57cc3a18b56ffa34226c153e64996f200ded38d457e48f3712 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def minOperations(self, nums: List[int], k: int) -> int:
        return sum(nums)%k
```
