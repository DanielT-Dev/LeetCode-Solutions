# Problem Statement: [https://leetcode.com/problems/minimum-number-of-removals-to-make-mountain-array/description/](https://leetcode.com/problems/minimum-number-of-removals-to-make-mountain-array/description/)
# My Solution: 
```
class Solution:
    def minimumMountainRemovals(self, nums: List[int]) -> int:
        n = len(nums)

        # Longest Increasing Subsequence (LIS) with DP
        lesser_left = []
        lesser_left.append(1)

        for i in range(1, n):
            lesser_left.append(1)
            for j in range(i):
                if nums[j] < nums[i]:
                    lesser_left[i] = max(lesser_left[i], 1 + lesser_left[j])

        # Longest Decreasing Subsequence (LDS) with DP
        lesser_right = [1] * n

        for i in range(n - 2, -1, -1):
            for j in range(n - 1, i, -1):
                if nums[j] < nums[i]:
                    lesser_right[i] = max(lesser_right[i], 1 + lesser_right[j])


        # Debugging
        # print(lesser_left)
        # print(lesser_right)

        best = 0

        # We go over all elements and try to pick them as the top of the mountain
        # Note that the first and last elements can not be considered the top of a mountain
        # That is because there is no left side (or right side respectively)
        for i in range(1, n - 1):
            # The LIS and LDS must have at least 1 other element than the top of the mountain (so at least length of 2)
            if lesser_left[i] == 1 or lesser_right[i] == 1:
                continue
            best = max(best, lesser_left[i] + lesser_right[i] - 1)
            # Note that we remove the top of the mountain itself because it was added 2 times in the formula

        return n - best
```
