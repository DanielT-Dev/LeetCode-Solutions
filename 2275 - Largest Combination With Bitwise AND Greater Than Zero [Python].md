# Problem Statement: [https://leetcode.com/problems/largest-combination-with-bitwise-and-greater-than-zero/](https://leetcode.com/problems/largest-combination-with-bitwise-and-greater-than-zero/)
# My Solution: 
```py
class Solution:
    def largestCombination(self, nums: List[int]) -> int:

        sums = [0] * 24
        mask = 1

        for p in range(24):
            for n in nums:
                if n & mask:
                    sums[p] += 1

            mask = mask << 1
        
        return max(sums)
```
