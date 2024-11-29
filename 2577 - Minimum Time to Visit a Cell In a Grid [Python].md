# Problem Statement: [https://leetcode.com/problems/minimum-time-to-visit-a-cell-in-a-grid/description/](https://leetcode.com/problems/minimum-time-to-visit-a-cell-in-a-grid/description/)
# My Solution: 
```py
from heapq import heappush, heappop

class Solution:
    def minimumTime(self, grid: List[List[int]]) -> int:
        m, n = len(grid), len(grid[0])
        counter = [[float('inf')] * n for _ in range(m)]

        def is_valid(i, j):
            return 0 <= i < m and 0 <= j < n

        moves = [(-1, 0), (1, 0), (0, 1), (0, -1)]

        heap = []
        heappush(heap, (0, 0, 0))
        counter[0][0] = 0

        if grid[0][1] > 1 and grid[1][0] > 1:
            return -1

        while heap:
            current, a, b = heappop(heap)

            if (a, b) == (m - 1, n - 1):
                return current

            for ip, jp in moves:
                ni, nj = ip + a, jp + b
                if is_valid(ni, nj):
                    aux = 0
                    if current + 1 < grid[ni][nj]:
                        aux = grid[ni][nj]
                        if (grid[ni][nj] - current - 1) % 2 != 0:
                            aux += 1
                    else:
                        aux = current + 1

                    if aux < counter[ni][nj]:
                        heappush(heap, (aux, ni, nj))
                        counter[ni][nj] = aux

        return -1 if counter[m - 1][n - 1] == float('inf') else counter[m - 1][n - 1]
```
