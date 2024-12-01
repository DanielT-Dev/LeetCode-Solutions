# Problem Statement: [https://leetcode.com/problems/check-if-n-and-its-double-exist/description/](https://leetcode.com/problems/check-if-n-and-its-double-exist/description/)
# My Solution: 
```py
class Solution:
    def checkIfExist(self, arr: List[int]) -> bool:

        d = {}
        counter = 0

        for x in arr:
            if x == 0:
                counter += 1
            d[x] = True

        if counter > 1:
            return True

        for x in arr:
            if 2 * x in d and x != 0:
                return True

        return False
```
