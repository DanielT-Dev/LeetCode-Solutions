https://leetcode.com/problems/number-of-closed-islands/description/

```py
class Solution:
    def closedIsland(self, grid: list[list[int]]) -> int:
        # Time complexity O(n*m) for step by step matrix traversal
        # Space complexity O(1) constant
        
        m = len(grid)
        n = len(grid[0])
        result_counter = 0
        directions = [[-1, 0], [1, 0], [0, -1], [0, 1]]
        self.is_closed_island = True

        # check if an element is inside the matrix
        def is_in_matrix(i, j):
            return i >= 0 and i < m and j >= 0 and j < n

        def explore(i, j):

            # mark it with a different value representing land that has been explored and should not be explored again
            grid[i][j] = -1  

            # explore all 4 directions
            for direction in directions:
                # calculate the new position's coordinates
                new_i = i + direction[0]
                new_j = j + direction[1]

                if is_in_matrix(new_i, new_j) == False:
                    self.is_closed_island = False # Mark that the island is not closed by water since it neighbors the edge of the matrix

                # go only inside the matrix and go only on unexplored land
                if is_in_matrix(new_i, new_j) and grid[new_i][new_j] == 0:
                    explore(new_i, new_j)

        for i in range(m):
            for j in range(n):
                if grid[i][j] == 0: # if we have found land, let's explore the island
                    self.is_closed_island = True # before exploring, always assume that the island is closed by water

                    explore(i, j)

                    if self.is_closed_island: 
                        result_counter += 1 # count the island

        return result_counter
```
