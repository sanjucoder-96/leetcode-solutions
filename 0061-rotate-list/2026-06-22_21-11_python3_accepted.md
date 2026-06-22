# 61. Rotate List
  
<br>**Problem:** https://leetcode.com/problems/rotate-list/<br>

**Difficulty:** Medium<br>
**Topics:** Linked List, Two Pointers<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-22 21:11 local time

**Runtime:** 4 ms (beats 5.369500000000004%)
**Memory:** 19.4 MB (beats 8.526700000000005%)


<!-- leetgit:submissionId=2042354141 codeHash=79a6ae94956683c51f2a63269b681f874715dc8bdc3ba5986af78903cea00810 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def rotateRight(self, head: Optional[ListNode], k: int) -> Optional[ListNode]:
        if not head or not head.next :
            return head
        temp,len=head,0
        while temp:
            len+=1
            temp=temp.next
        k%=len
        if k==0 or len==1:
            return head
        temp=head
        for i in range(len-k-1):
            temp=temp.next
        n=temp.next
        temp.next=None
        x=n
        while x.next:
            x=x.next
        x.next=head
        return n
        
```
