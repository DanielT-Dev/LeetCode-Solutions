# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-candies-allocated-to-k-children/description/?envType=daily-question&envId=2025-03-14)
# My Solution: 
```python
class Solution:
    def maximumCandies(self, candies: List[int], k: int) -> int:
        
        n = len(candies)

        left = 1
        right = sum(candies) // k
        result = 0

        # Time complexity O(log n)
        while left <= right:
            mid = (left + right) // 2

            if sum(x // mid for x in candies) >= k:
                result = mid
                left = mid + 1
            else:
                right = mid - 1
        
        return result
```
