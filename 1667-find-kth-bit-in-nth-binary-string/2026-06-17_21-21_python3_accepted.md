# 1667. Find Kth Bit in Nth Binary String
  
<br>**Problem:** https://leetcode.com/problems/find-kth-bit-in-nth-binary-string/<br>

**Difficulty:** Medium<br>
**Topics:** String, Recursion, Simulation<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-17 21:21 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.4 MB (beats 44.26929999999999%)


<!-- leetgit:submissionId=2036561139 codeHash=e6ee055ae08951463cefe68141495a0726b21b6ce49b9ec35044da76a9b1ae9b notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def findKthBit(self, n: int, k: int) -> str:
        if n==1:
            return "0"
        total_len= (1<<n)-1
        mid = 1<<(n-1)
        if k==mid:
            return "1"
        if k>mid:
            mirror_idx=total_len-k+1
            bit=self.findKthBit(n-1,mirror_idx)
            return "1" if bit=="0" else "0"
        else:
            return self.findKthBit(n-1,k)
        
```
