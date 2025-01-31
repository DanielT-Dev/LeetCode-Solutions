# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/making-a-large-island/description/?envType=daily-question&envId=2025-01-31)
# My Solution: 
```python
class Solution:
    def largestIsland(self, grid: List[List[int]]) -> int:
        
        n = len(grid)

        father = {}
        size = [0]

        directions = [(1, 0), (0, 1), (-1, 0), (0, -1)]

        zero = False

        def is_valid(i, j):
            return i >= 0 and i < n and j >= 0 and j < n

        def DFS(i, j):
            # Use a Depth-First Search (DFS) on land elements to find the size of the island

            total = 1

            for di, dj in directions:

                ni = i + di
                nj = j + dj

                if not is_valid(ni, nj):
                    continue

                # Explore adjacent element only if it has not been visited already
                if (ni, nj) not in father and grid[ni][nj] == 1:

                    father[(ni, nj)] = father[(i, j)]

                    total += DFS(ni, nj)

            return total

        # Store number of islands
        k = 0

        for i in range(n):
            for j in range(n):
                
                # Start a new DFS for the island only if it has not been visited already
                if grid[i][j] == 1 and (i, j) not in father:
                    
                    # Update number of islands
                    k += 1

                    # Assign the island index to the father element (Union Find)
                    father[(i, j)] = k
                    
                    size.append(DFS(i, j))
                
                # Check if matrix contains at least 1 water element
                if grid[i][j] == 0:
                    zero = True

        result = 0

        # Special case if all elements are 1 (land)
        if zero == False:
            return n ** 2

        for i in range(n):
            for j in range(n):
                
                # Calculate the maximum island size if we transform this element from 0 to 1
                if grid[i][j] == 0:

                    total = 1

                    # Avoid adding duplicate island sizes
                    islands = set()

                    for di, dj in directions:

                        ni = i + di
                        nj = j + dj

                        if not is_valid(ni, nj):
                            continue

                        if grid[ni][nj] == 1:

                            island_index = father[(ni, nj)]

                            # Avoid adding duplicate island sizes
                            if island_index not in islands:
                                total += size[island_index]

                            islands.add(island_index)
                    
                    # Update maximum island size
                    result = max(result, total)

        return result
```
