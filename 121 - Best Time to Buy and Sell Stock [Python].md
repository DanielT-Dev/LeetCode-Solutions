# Problem Statement: [https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)
# My Solution: 
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        
        n = len(prices)

        best = [0] * n

        best[n - 1] = prices[n - 1]

        for i in range(n - 2, -1, -1):
            best[i] = max(prices[i], best[i + 1])

        maximum = 0

        for i in range(n):
            if best[i] - prices[i] > maximum:
                maximum = best[i] - prices[i]
        
        if maximum >= 0:
            return maximum
        else:
            return 0
```
