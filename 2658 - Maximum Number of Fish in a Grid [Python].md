# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-number-of-fish-in-a-grid/description/?envType=daily-question&envId=2025-01-28)
# My Solution: 
```python
class Solution:
    def findMaxFish(self, grid: List[List[int]]) -> int:
        m = len(grid)
        n = len(grid[0])
        
        # Directions for moving to adjacent cells (up, down, left, right)
        directions = [(-1, 0), (1, 0), (0, -1), (0, 1)]
        
        def dfs(i, j):
            # Base case: if the cell is out of bounds or is land (0), return 0
            if i < 0 or i >= m or j < 0 or j >= n or grid[i][j] == 0:
                return 0
            
            # Collect the fish in the current cell
            fish = grid[i][j]
            
            # Mark the cell as visited by setting it to 0 (land)
            grid[i][j] = 0
            
            # Explore all four directions
            for dx, dy in directions:
                fish += dfs(i + dx, j + dy)
            
            return fish
        
        max_fish = 0
        
        # Iterate through each cell in the grid
        for i in range(m):
            for j in range(n):
                if grid[i][j] > 0:  # If the cell is water
                    # Start DFS from this cell and update the maximum fish count
                    max_fish = max(max_fish, dfs(i, j))
        
        return max_fish
```
