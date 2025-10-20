# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/generate-parentheses/description/)
# My Solution: 
```python
class Solution:

    result = []
    l = 0

    def solve(self, n, op, s):
        # Heuristic Optimisation
        if n < self.l // 2 and op > n:
            return

        # Exit condition
        if n == 0:
            if op == 0:
                self.result.append(s)
            return

        # Recursive relation
        self.solve(n - 1, op + 1, s + '(')
        if op > 0:
            self.solve(n - 1, op - 1, s + ')')

    def generateParenthesis(self, n: int) -> List[str]:
        # Using Backtracking method
        # TC: O(2^n)
        # SC: O(w) where w is the number of well-formed configurations

        # Reset class variable
        self.result = []
        self.l = n

        self.solve(2 * n, 0, "")

        return self.result
```
