# Statement: [Link to Leetcode](https://leetcode.com/problems/find-the-punishment-number-of-an-integer/description/?envType=daily-question&envId=2025-02-15)
# Solution:
```python
class Solution:
    def punishmentNumber(self, n: int) -> int:
        
        def back(x, i, p, s, current):
            # Exit condition
            if p == len(x):
                return s + current == i

            # Partition the string at position p
            p1 = back(x, i, p + 1, s + current, int(x[p]))
            # Do not partition the string (continue to extend last partition)
            p2 = back(x, i, p + 1, s, current * 10 + int(x[p]))

            return False or p1 or p2

        result = 0

        for i in range(n + 1):
            x = i * i
            l = list(str(x))
            if back(l, i, 0, 0, 0):
                result += i * i

        return result
```
