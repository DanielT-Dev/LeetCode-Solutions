# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/solving-questions-with-brainpower/)
# My Solution: 
```python
class Solution:
    def mostPoints(self, questions: List[List[int]]) -> int:
        
        n = len(questions)

        dp = [0] * (n + 1)

        for i in range(n - 1, -1, -1):

            points, power = questions[i]

            if i + power + 1 < n:
                dp[i] = max(dp[i + 1], points + dp[i + power + 1])
            else:
                dp[i] = max(dp[i + 1], points)

        return dp[0]

```
