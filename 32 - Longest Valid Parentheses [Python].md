# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-valid-parentheses/description/)
# My Solution: 
```python
class Solution:
    def longestValidParentheses(self, s: str) -> int:
        # TC: O(n) liniar
        # SC: O(n) for the stack data structure

        n = len(s)
        stack = [-1]
        max_length = 0

        for i in range(n):
            if s[i] == '(':
                stack.append(i)
            if s[i] == ')':
                stack.pop()

                if len(stack) == 0:
                    stack.append(i)
                else:
                    max_length = max(max_length, i - stack[-1])

        return max_length            
```
