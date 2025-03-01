# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/apply-operations-to-an-array/?envType=daily-question&envId=2025-03-01)
# My Solution: 
```python
class Solution:
    def applyOperations(self, nums: List[int]) -> List[int]:
        n = len(nums)
        
        # Apply operations
        for i in range(n - 1):
            if nums[i] == nums[i + 1]:
                nums[i] *= 2
                nums[i + 1] = 0
        
        # Shift zeros to the end (in-place)
        non_zero_idx = 0
        
        # Move all non-zero elements to the front
        for i in range(n):
            if nums[i] != 0:
                nums[non_zero_idx] = nums[i]
                non_zero_idx += 1
        
        # Fill the remaining positions with zeros
        for i in range(non_zero_idx, n):
            nums[i] = 0
        
        return nums
        
```
