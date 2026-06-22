# 61. Rotate List
  
<br>**Problem:** https://leetcode.com/problems/rotate-list/<br>

**Difficulty:** Medium<br>
**Topics:** Linked List, Two Pointers<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-22 21:29 local time

**Runtime:** 2 ms (beats 17.223600000000005%)
**Memory:** 19.5 MB (beats 8.526700000000005%)


<!-- leetgit:submissionId=2042375277 codeHash=29af15e5d35b772add86d1fc35036fa635e7bc8df86e4dc1e25c20fc15a6ac48 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def rotateRight(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        if not head :
            return head
        len=1
        dummy=head
        while dummy.next:
            len+=1
            dummy=dummy.next
        k%=len
        if k==0 :
            return head
        temp=head
        for _ in range(len-k-1):
            temp=temp.next
        newHead=temp.next
        temp.next=None
        dummy.next=head
        return newHead


        
```
