# Problem statement: [link to the problem](https://leetcode.com/problems/smallest-missing-non-negative-integer-after-operations/?envType=daily-question&envId=2025-10-16)
# My Solution:
```py
class Solution:
    def findSmallestInteger(self, nums: List[int], value: int) -> int:
        # TC: O(n) due to iteration of list elements
        # SC: O(value) due to storing the frequency of all
        # possible % value results
        
        results = [0 for i in range(value)]

        for x in nums:
            t = x % value
            results[t] += 1
        
        # Find the index of the first element with minimum frequency
        i = results.index(min(results))

        return results[i] * value + i

```
