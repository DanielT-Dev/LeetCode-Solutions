# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/find-minimum-cost-to-remove-array-elements/description/)
# My Solution: 
```python
class Solution:

    @cache
    def dfs(self, a, i):
        n = self.n
        nums = self.nums

        if i == n:
            return a

        b = nums[i]

        if i + 1 == n:
            return max(a, b)

        c = nums[i + 1]

        a_cost = max(b, c) + self.dfs(a, i + 2)
        b_cost = max(a, c) + self.dfs(b, i + 2)
        c_cost = max(a, b) + self.dfs(c, i + 2)
        return min(a_cost, b_cost, c_cost)

    def minCost(self, nums: List[int]) -> int:
        self.n = len(nums)
        self.nums = nums

        return self.dfs(nums[0], 1)
```
