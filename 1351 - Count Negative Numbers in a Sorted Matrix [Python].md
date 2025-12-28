# Problem Statement: [https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/description/?envType=daily-question&envId=2025-12-28](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/description/?envType=daily-question&envId=2025-12-28)
# My Solution: 
```python
class Solution:
    def countNegatives(self, grid: List[List[int]]) -> int:
        
        n = len(grid)
        m = len(grid[0])
        i = n - 1
        j = 0
        total = 0
        
        while i >= 0 and j < m:
            if grid[i][j] < 0:
                total += m - j
                i -= 1
            else:
                j += 1
        
        return total
```
