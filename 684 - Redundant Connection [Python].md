# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/redundant-connection/description/?envType=daily-question&envId=2025-01-29)
# My Solution: 
```python
class Solution:
    def findRedundantConnection(self, edges: List[List[int]]) -> List[int]:
        
        n = len(edges)

        father = [i for i in range(n + 1)]
        length = [1 for i in range(n + 1)]

        result = []

        def find_father(x):
            
            if father[x] == x:
                return x
            
            # Heuristic Memoization
            father[x] = find_father(father[x])

            return father[x]

        for a, b in edges:

            fa = find_father(a)
            fb = find_father(b)

            # Detect cycle
            if fa == fb:
                result = [a, b]

            # Disjoint Set Union (DSU)
            if length[fa] > length[fb]:

                father[fb] = fa
                length[fa] += length[father[b]]

            elif length[father[a]] <= length[father[b]]:

                father[fa] = fb
                length[fb] += length[father[a]]

        return result
```
