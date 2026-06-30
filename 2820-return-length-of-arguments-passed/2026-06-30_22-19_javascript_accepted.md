# 2820. Return Length of Arguments Passed
  
<br>**Problem:** https://leetcode.com/problems/return-length-of-arguments-passed/<br>

**Difficulty:** Easy<br>
**Topics:** None<br>
**Language:** javascript<br>
**Status:** Accepted<br>
**Submitted:** 2026-06-30 22:19 local time

**Runtime:** 49 ms (beats 22.004899999999992%)
**Memory:** 53.9 MB (beats 22.737699999999982%)


<!-- leetgit:submissionId=2051461770 codeHash=ca2aa59cbbc04e63d6d10f3d0b8defc12da36cae85b6f8f4be458b1193e198fe notesHash=e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855 -->

## Solution

```javascript
/**
 * @param {...(null|boolean|number|string|Array|Object)} args
 * @return {number}
 */
var argumentsLength = function(...args) {
    return args.length;
};

/**
 * argumentsLength(1, 2, 3); // 3
 */
```
