# Problem Statement: [https://leetcode.com/problems/rotate-string/](https://leetcode.com/problems/rotate-string/)
# My Solution: 
```
class Solution:
    def rotateString(self, s: str, goal: str) -> bool:
        if len(s) != len(goal):
            return False
        return goal in s + s
```
