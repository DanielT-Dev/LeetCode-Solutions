# Problem Statement: [https://leetcode.com/problems/count-unguarded-cells-in-the-grid/description/](https://leetcode.com/problems/count-unguarded-cells-in-the-grid/description/)
# My Solution: 
```py
class Solution:
    def countUnguarded(self, m: int, n: int, guards: List[List[int]], walls: List[List[int]]) -> int:
        s = set()

        is_wall = {}
        is_guard = {}

        for wall in walls:
            iw = wall[0]
            jw = wall[1]

            is_wall[(iw, jw)] = True

        for guard in guards:
            ig = guard[0]
            jg = guard[1]

            is_guard[(ig, jg)] = True

        for guard in guards:
            ig = guard[0]
            jg = guard[1]

            i = ig - 1
            while i >= 0:
                if (i, jg) in is_wall or (i, jg) in is_guard:
                    break 
                s.add((i, jg))
                i -= 1
            
            i = ig + 1
            while i < m:
                if (i, jg) in is_wall or (i, jg) in is_guard:
                    break
                s.add((i, jg))
                i += 1
            
            j = jg - 1
            while j >= 0:
                if (ig, j) in is_wall or (ig, j) in is_guard:
                    break
                s.add((ig, j))
                j -= 1
            
            j = jg + 1
            while j < n:
                if (ig, j) in is_wall or (ig, j) in is_guard:
                    break
                s.add((ig, j))
                j += 1

        print(s)

        return m*n - len(s) - len(walls) - len(guards)

```
