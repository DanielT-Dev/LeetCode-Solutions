# Problem Statement: [https://leetcode.com/problems/maximal-square/description/](https://leetcode.com/problems/maximal-square/description/)
# My Solution: 
```py
class Solution:
    def maximalSquare(self, matrix: List[List[str]]) -> int:

        m = len(matrix)
        n = len(matrix[0])

        dp = [[0] * n for _ in range(m)]

        result = 0

        for i in range(m):
            for j in range(n):
                if matrix[i][j] == '1':
                    
                    if i == 0 or j == 0:
                        dp[i][j] = 1
                    else:
                        dp[i][j] = min(dp[i - 1][j - 1], dp[i - 1][j], dp[i][j - 1]) + 1

                result = max(result, dp[i][j])

        return result ** 2
```
