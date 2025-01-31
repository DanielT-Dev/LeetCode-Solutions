# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/shortest-subarray-with-or-at-least-k-i/description/)
# My Solution: 
```python
class Solution:
    def minimumSubarrayLength(self, nums: List[int], k: int) -> int:
        n = len(nums)
        min_len = float('inf')
        for i in range(n):
            curr = 0
            for j in range(i, n):
                curr |= nums[j]
                if curr >= k:
                    min_len = min(min_len , j - i + 1)
                    break
        return min_len if min_len != float('inf') else -1
```
