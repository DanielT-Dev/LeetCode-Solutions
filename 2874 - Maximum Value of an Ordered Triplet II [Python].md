# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-value-of-an-ordered-triplet-ii/?envType=daily-question&envId=2025-04-03)
# My Solution: 
```python
class Solution:
    def maximumTripletValue(self, nums: List[int]) -> int:
        
        n = len(nums)

        result = 0

        # Store maximum element untill 'i'th positon from both left and right directions
        left = [0] * n
        right = [0] * n

        left[0] = nums[0]
        right[0] = nums[n - 1]

        # Time Complexity: O(n) [linear]
        for i in range(1, n):
            left[i] = max(left[i - 1], nums[i])
        for i in range(n - 2, -1, -1):
            right[n - i - 1] = max(right[n - i - 2], nums[i])

        # First and last indices can not be picked as middle indices
        # => ignore first and last indices
        for i in range(1, n - 1):

            if((left[i - 1] - nums[i]) * right[n - i - 2] > result):

                result = (left[i - 1] - nums[i]) * right[n - i - 2]
            # Notice: since left and right arrays include 'i'th element
            # we can exclude it by adding -1 to the indexation

        return result
```
