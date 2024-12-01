# Problem Statement: [https://leetcode.com/problems/target-sum/description/](https://leetcode.com/problems/target-sum/description/)
# My Solution: 
```py
class Solution:
    def findTargetSumWays(self, nums: List[int], target: int) -> int:

        n = len(nums)

        dp = {}

        if n == 1:
            if nums[0] == target or -nums[0] == target:
                return 1
            else:
                return 0

        def back(arr, index, s):

            if index == n:
                return 1 if target == s else 0

            if (index, s) in dp:
                return dp[(index, s)]

            ways = 0

            ways += back(arr, index + 1, s + arr[index])
            ways += back(arr, index + 1, s - arr[index])

            dp[(index, s)] = ways

            return ways


        return back(nums, 0, 0)
```
