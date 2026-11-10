https://leetcode.com/problems/climbing-stairs-ii/description/
```py
class Solution:
    def climbStairs(self, n: int, costs: List[int]) -> int:
        
        dp = [float("inf")] * (n + 10)
        dp[0] = 0

        for i in range(1, n + 1):
            m = dp[i - 1] + 1
            if i - 2 >= 0:
                m = min(m, dp[i - 2] + 4)
            if i - 3 >= 0:
                m = min(m, dp[i - 3] + 9)
            dp[i] = costs[i - 1] + m


        return dp[n]
```
