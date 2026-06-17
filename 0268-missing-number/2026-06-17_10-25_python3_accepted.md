# 268. Missing Number
  
<br>**Problem:** https://leetcode.com/problems/missing-number/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Hash Table, Math, Binary Search, Bit Manipulation, Sorting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-17 10:25 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 20.5 MB (beats 41.44679999999997%)


<!-- leetgit:submissionId=2035871775 codeHash=f62827cd78d57c638390de5f3aa2bd2b85e442258e96a6a390997f157418a27d notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        s=sum(nums)
        n=len(nums)
        return n*(n+1)//2 -s
```
