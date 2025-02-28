# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-increasing-subsequence/description/)
# My Solution: 
```python
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        
        n = len(nums)

        dp = [1] * n

        result = 1

        for i in range(n):

            length = 1
            a = nums[i]

            for j in range(i):

                b = nums[j]

                if a > b:

                    dp[i] = max(dp[j] + 1, dp[i])
            
            result = max(result , dp[i])
        
        return result
```
