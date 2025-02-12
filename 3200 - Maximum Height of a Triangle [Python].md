# Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-height-of-a-triangle/)
# Solution:
```python
class Solution:
    def maxHeightOfTriangle(self, red: int, blue: int) -> int:
        
        cred = red
        cblue = blue

        result = 0

        i = 1

        while True:

            if i % 2 == 1:
                if blue - i >= 0:
                    blue -= i
                    i += 1
                else:
                    break
            else:
                if red - i >= 0:
                    red -= i
                    i += 1
                else:
                    break

        result = max(result, i)

        i = 1

        while True:
            if i % 2 == 1:
                if cred - i >= 0:
                    cred -= i
                    i += 1
                else:
                    break
            else:
                if cblue - i >= 0:
                    cblue -= i
                    i += 1
                else:
                    break

        result = max(result, i)

        return result - 1
```
