# Problem Statement: [https://leetcode.com/problems/take-gifts-from-the-richest-pile/description/](https://leetcode.com/problems/take-gifts-from-the-richest-pile/description/)
# My Solution: 
```py
import heapq

class Solution:
    def pickGifts(self, gifts: List[int], k: int) -> int:
        
        pq = []

        for g in gifts:
            heapq.heappush(pq, -g)

        result = 0

        while pq and k:

            best = -heapq.heappop(pq)
            best = math.floor(math.sqrt(best))

            if best > 0:
                heapq.heappush(pq, -best)
            
            k -= 1

        result += -sum(pq)

        return result
```
