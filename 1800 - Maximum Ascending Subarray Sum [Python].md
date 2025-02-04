# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-ascending-subarray-sum/description/)
# My Solution: 
```python
class Solution:
    def maxAscendingSum(self, nums: List[int]) -> int:
        
        n = len(nums)
        result = float('-inf')

        elo_taxi = nums[0]

        for i in range(1, n):
            if nums[i - 1] < nums[i]:
                elo_taxi += nums[i]
            else:
                result = max(result, elo_taxi)
                elo_taxi = nums[i]
        
        result = max(result, elo_taxi)

        return result
            
```
