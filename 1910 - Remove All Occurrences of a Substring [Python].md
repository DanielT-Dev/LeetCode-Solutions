# Statement: [Link to Leetcode](https://leetcode.com/problems/remove-all-occurrences-of-a-substring/description/?envType=daily-question&envId=2025-02-11)
# Solution:
```python
class Solution:
    def removeOccurrences(self, s: str, part: str) -> str:
        
        s = list(s)
        n = len(s)
        m = len(part)

        stack = []

        for i in range(n):

            stack.append(s[i])
            
            if "".join(stack).endswith(part):
                for c in range(m):
                    stack.pop()

        return "".join(stack)
```
