# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/split-with-minimum-sum/)
# My Solution: 
```python
class Solution:
    def splitNum(self, num: int) -> int:
        
        result = float('inf')
        num = list(str(num))
        newNum = []
        n = len(num)

        for x in num:
            newNum.append(x)
        
        newNum.sort()

        a = []
        b = []

        for i in range(n):
            if i % 2 == 0:
                a.append(newNum[i])
            else:
                b.append(newNum[i])
        
        return int(''.join(a)) + int(''.join(b))
```
