# Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-operations-to-make-columns-strictly-increasing/description/)
# Solution:
```python
class Solution:
    def minimumOperations(self, grid: List[List[int]]) -> int:
        
        m = len(grid)
        n = len(grid[0])

        counter = 0

        for j in range(n):
            for i in range(1, m):

                if grid[i - 1][j] >= grid[i][j]:

                    counter += grid[i - 1][j] - grid[i][j] + 1
                    grid[i][j] = grid[i - 1][j] + 1

        return counter
```
