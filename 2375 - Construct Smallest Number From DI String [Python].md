# Statement: [Link to Leetcode](https://leetcode.com/problems/construct-smallest-number-from-di-string/description/?envType=daily-question&envId=2025-02-18)
# Solution 1 (Backtracking):
```python
class Solution:
    def smallestNumber(self, pattern: str) -> str:

        n = len(pattern)
        candidate = [0] * (n + 1)
        result = [9] * (n + 1)
        s = set()

        def backtracking(i):
            nonlocal candidate, result

            if i == n + 1:

                if candidate < result:
                    result = candidate[:]
                return 

            left = right = None
            if i == 0:
                left = 1
                right = 10
            elif pattern[i - 1] == 'I':
                left = candidate[i - 1] + 1
                right = 10
            elif pattern[i - 1] == 'D':
                left = 1
                right = candidate[i - 1]

            for j in range(left, right):
                if j not in s:

                    candidate[i] = j
                    s.add(j)
                    backtracking(i + 1)
                    s.remove(j)

        backtracking(0)

        return "".join([str(x) for x in result])
```
# Solution 2 (Stack):
```python
class Solution:
    def smallestNumber(self, pattern: str) -> str:
        result = []
        stack = []

        for i in range(len(pattern) + 1):
            stack.append(str(i + 1))
            if i == len(pattern) or pattern[i] == 'I':
                while stack:
                    result.append(stack.pop())

        return "".join(result)
```
