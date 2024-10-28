# Problem Statement: [https://leetcode.com/problems/minimum-moves-to-equal-array-elements-ii/description/](https://leetcode.com/problems/minimum-moves-to-equal-array-elements-ii/description/)
# My Solution: 
```
class Solution:
    def minMoves2(self, nums: List[int]) -> int:
        nums.sort()

        n = len(nums)
        k = 0
        t = 0

        if n == 1:
            return 0

        if n % 2 == 0:
            k = (nums[n // 2 - 1] + nums[n // 2]) // 2
        else:
            k = nums[n // 2]

        for n in nums:
            t += abs(n - k)

        return t
        

```
