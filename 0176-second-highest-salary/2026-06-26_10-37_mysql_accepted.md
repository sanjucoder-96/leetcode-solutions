# 176. Second Highest Salary
  
<br>**Problem:** https://leetcode.com/problems/second-highest-salary/<br>

**Difficulty:** Medium<br>
**Topics:** Database<br>
**Language:** mysql<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-26 10:37 local time

**Runtime:** 295 ms (beats 39.22320000000005%)
**Memory:** 0 MB (beats 100%)


<!-- leetgit:submissionId=2046409149 codeHash=8540e6e3947773f4ad97ef5229805b77e6b8be7e7e666390e6821e86e59356d0 notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```mysql
# Write your MySQL query statement below
select MAX(salary) as SecondHighestSalary  from employee where salary<(select MAX(salary) from employee);
```
