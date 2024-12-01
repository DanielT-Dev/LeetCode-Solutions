# Problem Statement: [https://leetcode.com/problems/jump-game-ii/description/](https://leetcode.com/problems/jump-game-ii/description/)
# My Solution: 
```py
class Solution:
    def jump(self, nums: List[int]) -> int:
        
        l = r = 0
        result = 0
        far = 0

        n = len(nums) - 1

        while r < n:
            for i in range(l, r + 1):
                far = max(far, nums[i] + i)

            l = r
            r = far

            result += 1

        return result
```
