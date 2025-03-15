# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/house-robber-iv/description/?envType=daily-question&envId=2025-03-15)
# My Solution: 
```python
class Solution:
    def minCapability(self, nums: List[int], k: int) -> int:
        
        n = len(nums)
        left = min(nums)
        right = max(nums)

        def check(guess):
            p1 = 0
            i = 0
            while i < n:
                if nums[i] <= guess:
                    p1 += 1
                    i += 2
                else:
                    i += 1
            p2 = 0
            i = 0
            while i < n:
                if nums[i] <= guess:
                    p2 += 1
                    i += 2
                else:
                    i += 1
            return p1 >= k or p2 >= k

        # Binary Search
        while left < right:

            mid = (left + right) // 2

            if check(mid):
                right = mid
            else:
                left = mid + 1
        
        return left
```
