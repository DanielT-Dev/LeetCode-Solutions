# Problem Statement: [https://leetcode.com/problems/evaluate-reverse-polish-notation/description/?envType=problem-list-v2&envId=dsa-linear-shoal-stack](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/?envType=problem-list-v2&envId=dsa-linear-shoal-stack)
# My Solution: 
```python
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:

        stack = []
        operators = set(['+', '-', '*', '/'])
        result = 0

        def helper(operator, a, b):
            if operator == '+':
                return a + b
            elif operator == '-':
                return b - a
            elif operator == '*':
                return a * b
            else:
                return b / a

        for token in tokens:
            if token not in operators:
                stack.append(token)
                continue
            stack.append(helper(token, int(stack.pop()), int(stack.pop())))
        
        return int(stack.pop())
```
