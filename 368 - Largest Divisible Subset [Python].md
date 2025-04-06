# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/largest-divisible-subset/description/?envType=daily-question&envId=2025-04-06)
# My Solution: 
```python
class Solution:
    def largestDivisibleSubset(self, nums: List[int]) -> List[int]:
        
        nums.sort()

        dp = [[n] for n in nums]

        for i in range(len(nums)):
            for j in range(i):
                if nums[i] % nums[j] == 0 and len(dp[j]) + 1 > len(dp[i]):
                    dp[i] = dp[j] + [nums[i]]

        return max(dp, key=len)
```
