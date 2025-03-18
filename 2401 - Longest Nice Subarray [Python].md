# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-nice-subarray/?envType=daily-question&envId=2025-03-18)
# My Solution: 
```python
from typing import List

class Solution:
    def longestNiceSubarray(self, nums: List[int]) -> int:
        left = 0
        used = 0
        result = 0
        n = len(nums)

        for right in range(n):
            while (used & nums[right]) != 0:
                used ^= nums[left]
                left += 1

            used |= nums[right]
            
            result = max(result, right - left + 1)

        return result

```
