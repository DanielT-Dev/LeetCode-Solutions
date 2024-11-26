# Problem Statement: [https://leetcode.com/problems/find-champion-ii/description/](https://leetcode.com/problems/find-champion-ii/description/)
# My Solution: 
```py
class Solution:
    def findChampion(self, n: int, edges: List[List[int]]) -> int:

        degree = [0] * n

        for edge in edges:
            degree[edge[1]] += 1

        counter = 0
        res = 0

        for i in range(n):
            if degree[i] == 0:
                res = i
                counter += 1

        if counter > 1:
            return -1

        return res
```
