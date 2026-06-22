# 61. Rotate List
  
<br>**Problem:** https://leetcode.com/problems/rotate-list/<br>

**Difficulty:** Medium<br>
**Topics:** Linked List, Two Pointers<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-22 21:30 local time

**Runtime:** 0 ms (beats 100%)
**Memory:** 19.3 MB (beats 36.178000000000004%)


<!-- leetgit:submissionId=2042375926 codeHash=57ff1a18c84118faa6c584c271c35d32a9641ed89c93e067cbb3329b3242e2b8 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def rotateRight(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        if not head or not head.next:
            return head
        len=1
        dummy=head
        while dummy.next:
            len+=1
            dummy=dummy.next
        k%=len
        if k==0 or len==1:
            return head
        temp=head
        for _ in range(len-k-1):
            temp=temp.next
        newHead=temp.next
        temp.next=None
        dummy.next=head
        return newHead


        
```
