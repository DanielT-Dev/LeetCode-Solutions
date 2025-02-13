# Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-operations-to-exceed-threshold-value-ii/)
# Solution:
```python
class Solution:
    def minOperations(self, nums: List[int], k: int) -> int:
        
        heapq.heapify(nums)

        counter = 0

        while len(nums) >= 2:

            x = heapq.heappop(nums)
            y = heapq.heappop(nums)

            if x >= k:
                break

            heapq.heappush(nums, x * 2 + y)

            counter += 1
        
        return counter
```
