# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/partition-equal-subset-sum/?envType=daily-question&envId=2025-04-07)
# My Solution: 
```python
class Solution:
    def canPartition(self, nums: List[int]) -> bool:
        
        sum_total = sum(nums)

        if sum_total % 2 != 0:
            return False

        sum_target = sum_total // 2

        dp = [False] * (sum_target + 1)
        
        dp[0] = True

        for n in nums:
            for i in range(sum_target, n - 1, -1):
                dp[i] = dp[i] | dp[i - n]

        return dp[sum_target]
```
