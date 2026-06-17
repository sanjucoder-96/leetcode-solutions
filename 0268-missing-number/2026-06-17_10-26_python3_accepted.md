# 268. Missing Number
  
<br>**Problem:** https://leetcode.com/problems/missing-number/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Hash Table, Math, Binary Search, Bit Manipulation, Sorting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-17 10:26 local time

**Runtime:** 3 ms (beats 60.176%)
**Memory:** 20.3 MB (beats 75.51879999999997%)


<!-- leetgit:submissionId=2035873358 codeHash=fe543a37ab21e1a02c39c240091f6e450e0c9a0890e02286db9b06b146c8c36e notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        x,n=0,len(nums)
        for i in range(1,n+1):
            x^=i
        s=0
        for i in nums:
            s^=i
        return x^s
```
