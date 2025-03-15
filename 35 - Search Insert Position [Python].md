# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/search-insert-position/)
# My Solution: 
```python
class Solution:
    def searchInsert(self, nums: List[int], target: int) -> int:
        
        n = len(nums)
        left = 0
        right = n - 1

        index = -1

        if target <= min(nums):
            return 0

        if target > max(nums):
            return n


        while left <= right:

            mid = (left + right) // 2

            if nums[mid] == target:
                return mid

            elif nums[mid] < target:

                index = mid + 1
                left = mid + 1

            else:
                right = mid - 1
        
        return index
```
