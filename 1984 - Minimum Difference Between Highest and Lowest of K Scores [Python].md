# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-difference-between-highest-and-lowest-of-k-scores/description/)
# My Solution: 
```python
class Solution:
    def minimumDifference(self, nums: List[int], k: int) -> int:
        
        if k == 1:
            return 0
        
        n = len(nums)
        nums.sort()
        result = float("inf")

        i = 0
        j = k

        while j <= n:
            a, b = nums[i], nums[j - 1]
            result = min(result, b - a)
            i += 1
            j += 1

        return result
```
