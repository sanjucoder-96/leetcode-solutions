# 2210. Find Target Indices After Sorting Array
  
<br>**Problem:** https://leetcode.com/problems/find-target-indices-after-sorting-array/<br>

**Difficulty:** Easy<br>
**Topics:** Array, Binary Search, Sorting<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-10-19 14:34 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.4 MB (beats 24.19899999999999%)


<!-- leetgit:submissionId=2176071148 codeHash=668ab47eed1d56d3ea7a9515c9fd5db458e5e3f08f2d473b52ccf1825fb4cb98 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def targetIndices(self, nums: list[int], target: int) -> list[int]:
        nums=sorted(nums)
        return [i for i in range((len((nums)))) if nums[i]==target]
        
```
