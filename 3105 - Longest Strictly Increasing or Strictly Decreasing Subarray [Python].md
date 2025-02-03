# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-strictly-increasing-or-strictly-decreasing-subarray/description/?envType=daily-question&envId=2025-02-03)
# My Solution: 
```python
class Solution:
    def longestMonotonicSubarray(self, nums: List[int]) -> int:
        
        n = len(nums)

        maximum_increasing = 1

        start = 0

        for i in range(1, n):

            if nums[i - 1] < nums[i]:
                continue
            else:
                maximum_increasing = max(maximum_increasing, i - start)
                start = i

        maximum_increasing = max(maximum_increasing, n - start)

        maximum_decreasing = 1

        start = 0

        for i in range(1, n):

            if nums[i - 1] > nums[i]:
                continue
            else:
                maximum_decreasing = max(maximum_decreasing, i - start)
                start = i

        maximum_decreasing = max(maximum_decreasing, n - start)

        return max(maximum_increasing, maximum_decreasing)
```
