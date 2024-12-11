# Problem Statement: [https://leetcode.com/problems/maximum-beauty-of-an-array-after-applying-operation/description/](https://leetcode.com/problems/maximum-beauty-of-an-array-after-applying-operation/description/)
# My Solution: 
```py
class Solution:
    def maximumBeauty(self, nums: List[int], k: int) -> int:
        
        n = len(nums)

        nums.sort() 

        limit = nums[n - 1]

        result = 1

        # Linear Search for maximum possible beauty
        for i in range(1, limit + 1):

            value = i

            # Binary Search for insertion index in sorted array
            left_index = bisect.bisect_left(nums, value - k) + 1
            right_index = bisect.bisect_right(nums, value + k) - 1

            # Store maximum possible beauty seen until now
            result = max(result, right_index - left_index + 2)

        return result
```
