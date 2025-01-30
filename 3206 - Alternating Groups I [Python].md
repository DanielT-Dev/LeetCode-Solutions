# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/alternating-groups-i/description/)
# My Solution: 
```python
class Solution:
    def numberOfAlternatingGroups(self, colors: List[int]) -> int:
        
        n = len(colors)

        if n < 3:
            return 0
        
        result = 0

        for i in range(1, n - 1):

            if colors[i] == 0:
                if colors[i - 1] == 1 and colors[i + 1] == 1:
                    result += 1
            if colors[i] == 1:
                if colors[i - 1] == 0 and colors[i + 1] == 0:
                    result += 1

        if colors[0] == 0:
            if colors[n - 1] == 1 and colors[1] == 1:
                result += 1
        else:
            if colors[n - 1] == 0 and colors[1] == 0:
                result += 1

        if colors[n - 1] == 0:
            if colors[0] == 1 and colors[n - 2] == 1:
                result +=1
        else:
            if colors[0] == 0 and colors[n - 2] == 0:
                result += 1

        return result
```
