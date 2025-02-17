# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/letter-tile-possibilities/?envType=daily-question&envId=2025-02-17)
# My Solution: 
```python
class Solution:
    def numTilePossibilities(self, tiles: str) -> int:
        
        n = len(tiles)
        used = [False] * n
        sequence = [-1] * n
        s = set()

        def backtracking(i):

            # Exit condition
            if i > n:
                return
            
            # Try every posibility
            for j in range(n):
                if not used[j]:

                    sequence[i] = tiles[j]
                    used[j] = True

                    str_sequence = "".join(sequence[:i + 1])

                    s.add(str_sequence)

                    backtracking(i + 1)

                    used[j] = False

        backtracking(0)

        return len(s)


```
