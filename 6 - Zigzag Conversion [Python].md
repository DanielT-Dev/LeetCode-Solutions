# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/zigzag-conversion/)
# My Solution: 
```python
class Solution:
    def convert(self, s: str, numRows: int) -> str:
        
        n = len(s)
        counter = 0 
        down = True

        if numRows == 1:
            return s

        result = [[''] for _ in range(numRows)]

        for ch in s:
            
            if counter == numRows - 1:
                down = False
            elif counter == 0:
                down = True
            
            if down:

                result[counter].append(ch)
                counter += 1
            
            else:
                result[counter].append(ch)
                counter -= 1

        return ''.join(''.join(x) for x in result)
```
