# Problem Statement: [https://leetcode.com/problems/maximum-number-of-integers-to-choose-from-a-range-i/description/](https://leetcode.com/problems/maximum-number-of-integers-to-choose-from-a-range-i/description/)
# My Solution: 
```py
class Solution:
    def maxCount(self, banned: List[int], n: int, maxSum: int) -> int:

        d = {}

        for x in banned:
            d[x] = True

        s = 0
        c = 0

        for i in range(1, n + 1):
            if i not in d:
                s += i

                if s > maxSum:
                    break

                c += 1
        
        return c
```
