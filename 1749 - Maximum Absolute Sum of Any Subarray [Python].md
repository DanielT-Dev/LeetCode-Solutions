# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-absolute-sum-of-any-subarray/?envType=daily-question&envId=2025-02-26)
# My Solution: 
```python
class Solution:
    def maxAbsoluteSum(self, nums: List[int]) -> int:
        
        n = len(nums)

        max_sum = 0
        s = 0

        for i in range(n):
            s += nums[i]

            if s < 0:
                s = 0

            max_sum = max(max_sum, s)

        min_sum = 0
        s = 0

        for i in range(n):
            s += nums[i]

            if s > 0:
                s = 0

            min_sum = min(min_sum, s)

        return max(max_sum, -min_sum)
```
