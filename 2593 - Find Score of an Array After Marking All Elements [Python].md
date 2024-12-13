# Problem Statement: [https://leetcode.com/problems/find-score-of-an-array-after-marking-all-elements/description/](https://leetcode.com/problems/find-score-of-an-array-after-marking-all-elements/description/)
# My Solution: 
```py
class Solution:
    def findScore(self, nums: List[int]) -> int:

        # Store (element, index) pairs in priority queue / min heap of tuples
        pq = []

        for i, n in enumerate(nums):
            heapq.heappush(pq, (n, i))

        # Store marked indices in set
        marked = set()
        s = 0

        while pq:
            n, i = heapq.heappop(pq)

            if i not in marked:
                # Mark current index and adjacent indices
                marked.add(i - 1)
                marked.add(i)
                marked.add(i + 1)
                
                s += n

        return s
```
