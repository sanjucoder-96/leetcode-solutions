# 13. Roman to Integer
  
<br>**Problem:** https://leetcode.com/problems/roman-to-integer/<br>

**Difficulty:** Easy<br>
**Topics:** Hash Table, Math, String<br>
**Language:** python3<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-24 11:32 local time

**Runtime:** 7 ms (beats 42.31950000000002%)
**Memory:** 19.2 MB (beats 88.47549999999998%)


<!-- leetgit:submissionId=2044194942 codeHash=7e68a85a3b47f96cfe81c5fb03f305efde5e596416d8dcc83feb334544623229 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```python3
class Solution:
    def romanToInt(self, s: str) -> int:
        mp={'I':1,'V':5,'X':10,'L':50,'C':100,'D':500,'M':1000}
        t=0
        for i in range(len(s)):
            if i+1<len(s) and mp[s[i]]<mp[s[i+1]]:
                t-=mp[s[i]]
            else:
                t+=mp[s[i]]
        return t
```
