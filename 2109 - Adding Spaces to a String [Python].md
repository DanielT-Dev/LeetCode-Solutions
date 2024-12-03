# Problem Statement: [https://leetcode.com/problems/adding-spaces-to-a-string/](https://leetcode.com/problems/adding-spaces-to-a-string/)
# My Solution: 
```py
class Solution:
    def addSpaces(self, s: str, spaces: List[int]) -> str:
        result = []
        k = 0
        n = len(spaces)

        for i, c in enumerate(s):

            if k < n and i == spaces[k] :
                result.append(" ")
                k += 1

            result.append(c)

        return "".join(result)
```
