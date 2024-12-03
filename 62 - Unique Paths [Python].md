# Problem Statement: [https://leetcode.com/problems/unique-paths/description/](https://leetcode.com/problems/unique-paths/description/)
# My Solution: 
```py
class Solution:
    def uniquePaths(self, m: int, n: int) -> int:
        
        dp = [[0] * (n + 1) for _ in range(m + 1)]

        for k in range(m + 1):
            dp[k][0] = 1
        for k in range(n + 1):
            dp[0][k] = 1

        MOD = 2 * (10 ** 9)

        for i in range(1, m + 1):
            for j in range(1, n + 1):
                dp[i][j] = (dp[i - 1][j] + dp[i][j - 1]) % MOD

        return dp[m - 1][n - 1]

```
