# Problem Statement: [https://leetcode.com/problems/maximum-matrix-sum/](https://leetcode.com/problems/maximum-matrix-sum/)
# My Solution: 
```py
class Solution:
    def maxMatrixSum(self, matrix: List[List[int]]) -> int:
        
        n = len(matrix)

        s = 0

        minimum = float("inf")

        counter = 0

        for r in matrix:
            for v in r:

                s += abs(v)

                if v < 0:
                    counter += 1

                minimum = min(minimum, abs(v))
            
        if counter % 2 == 0:
            return s
        return s - 2*minimum
```
