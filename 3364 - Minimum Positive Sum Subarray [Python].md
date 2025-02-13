# Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-positive-sum-subarray/description/)
# Solution:
```python
class Solution:
    def minimumSumSubarray(self, nums: List[int], l: int, r: int) -> int:
        
        n = len(nums)

        # Store prefix sums
        prefix_sums = [0] * (n + 1)

        # Compute prefix sums
        for i in range(1, n + 1):
            prefix_sums[i] = prefix_sums[i - 1] + nums[i - 1]

        result = float('inf')

        # Consider all lengths from range [l, r]
        for length in range(l, r + 1):

            # Sliding window method
            i = 1
            while i + length <= n + 1:
                s = prefix_sums[i + length - 1] - prefix_sums[i - 1]

                if s > 0:
                    result = min(result, s)

                i += 1

        if result == float('inf'):
            return -1

        return result
```
