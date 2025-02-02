# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/?envType=daily-question&envId=2025-02-02)
# My Solution: 
```python
class Solution:
    def check(self, nums: List[int]) -> bool:
        return len([i for i in range(len(nums)) if nums[(i + 1) % len(nums)] - nums[i] < 0]) <= 1
```
