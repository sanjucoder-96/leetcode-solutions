# 3065. Display the First Three Rows
  
<br>**Problem:** https://leetcode.com/problems/display-the-first-three-rows/<br>

**Difficulty:** Easy<br>
**Topics:** None<br>
**Language:** pythondata<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-17 10:16 local time

**Runtime:** 271 ms (beats 64.12790000000003%)
**Memory:** 66.5 MB (beats 22.651500000000006%)


<!-- leetgit:submissionId=2035862069 codeHash=c04a9ab2e82c76025428a74b89bcf0470a9f1c31918991b9574da13e7bea504c notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```pythondata
import pandas as pd

def selectFirstRows(employees: pd.DataFrame) -> pd.DataFrame:
        return employees.head(3)
```
