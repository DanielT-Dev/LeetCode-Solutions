# Statement: [Link to Leetcode](https://leetcode.com/problems/clear-digits/)
# Solution:
```python
class Solution:
    def clearDigits(self, s: str) -> str:
    
        n = len(s)

        s = list(s)

        stack = []

        for i in range(n):
            if s[i].isdigit():
                stack.pop()
            else:
                stack.append(s[i])

        return "".join(stack)
```
