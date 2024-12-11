# Problem Statement: [https://leetcode.com/problems/remove-duplicate-letters/description/](https://leetcode.com/problems/remove-duplicate-letters/description/)
# My Solution: 
```py
class Solution:
    def removeDuplicateLetters(self, s: str) -> str:
        
        stack = []
        seen = set()

        last = {c: i for i, c in enumerate(s)}

        for i, c in enumerate(s):
            if c not in seen:

                while stack and c < stack[-1] and i < last[stack[-1]]:
                    seen.remove(stack.pop())

                seen.add(c)
                stack.append(c)

        return "".join(stack)
```
