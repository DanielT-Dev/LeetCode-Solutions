# Problem Statement: [https://leetcode.com/problems/final-array-state-after-k-multiplication-operations-i/description/](https://leetcode.com/problems/final-array-state-after-k-multiplication-operations-i/description/)
# My Solution: 
```py
class Solution:
    def getFinalState(self, nums: List[int], k: int, multiplier: int) -> List[int]:
        
        pq = []

        for i, n in enumerate(nums):
            heapq.heappush(pq, (n, i))

        while k > 0:

            n, i = heapq.heappop(pq)

            heapq.heappush(pq, (n * multiplier, i))

            nums[i] = n * multiplier

            k -= 1

        return nums
```
