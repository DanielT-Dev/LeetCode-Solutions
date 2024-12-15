# Problem Statement: [https://leetcode.com/problems/maximum-average-pass-ratio/](https://leetcode.com/problems/maximum-average-pass-ratio/)
# My Solution: 
```py
class Solution:
    def maxAverageRatio(self, classes: List[List[int]], extraStudents: int) -> float:
        
        n = len(classes)

        extra = extraStudents

        classes = [
            (num / denom - (num + 1) / (denom + 1), num, denom)
            for num, denom in classes
        ]

        heapq.heapify(classes)

        while extra > 0:
            top = heapq.heappop(classes)

            _, num, denom = top

            heapq.heappush(classes, ((num + 1) / (denom + 1) - (num + 2) / (denom + 2), num + 1, denom + 1),)

            extra -= 1

        s = 0

        for e in classes:
            v, p, t = e

            s += v
        
        return s / n
```
