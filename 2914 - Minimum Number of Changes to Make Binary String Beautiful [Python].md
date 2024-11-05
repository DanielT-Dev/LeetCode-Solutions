# Problem Statement: [https://leetcode.com/problems/minimum-number-of-changes-to-make-binary-string-beautiful/description/](https://leetcode.com/problems/minimum-number-of-changes-to-make-binary-string-beautiful/description/)
# My Solution: 
```py
class Solution:
    def minChanges(self, s: str) -> int:

        l = len(s)

        counter = 0

        for i in range(1, l, 2):
            if s[i - 1] != s[i]:
                counter += 1
        
        return counter

        
```
