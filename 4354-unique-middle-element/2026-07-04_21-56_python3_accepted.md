# 4354. Unique Middle Element
  
<br>**Problem:** https://leetcode.com/problems/unique-middle-element/<br>

**Difficulty:** Easy<br>
**Topics:** None<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-07-04 21:56 local time

**Runtime:** 7 ms (beats 5.818399999999998%)
**Memory:** 19.4 MB (beats 19.365300000000005%)


<!-- leetgit:submissionId=2056018976 codeHash=57819bed30e82fa48e7509c8571e7f1114d41de6e0706ddbcc6e7e577a9db063 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
from collections import Counter
class Solution:
    def isMiddleElementUnique(self, nums: list[int]) -> bool:
        n=len(nums)
        mid=nums[n//2]
        s=Counter(nums)
        return s[mid]==1
        
```
