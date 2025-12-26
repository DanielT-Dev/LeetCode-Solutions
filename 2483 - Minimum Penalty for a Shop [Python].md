# Problem Statement: [https://leetcode.com/problems/minimum-penalty-for-a-shop/description/?envType=daily-question&envId=2025-12-26](https://leetcode.com/problems/minimum-penalty-for-a-shop/description/?envType=daily-question&envId=2025-12-26)
# My Solution: 
```python
class Solution:
    def bestClosingTime(self, customers: str) -> int:
        
        n = len(customers)
        yCount = nCount = 0
        
        for customer in customers:
            yCount += 1 if customer == 'Y' else 0
            nCount += 1 if customer == 'N' else 0
        
        if yCount == 0:
            return 0
        if yCount == n:
            return yCount
        
        yCurrent = nCurrent = result = 0
        minPenalty = yCount

        for i in range(n):
            if customers[i] == 'Y':
                yCurrent += 1
            else:
                nCurrent += 1
            if minPenalty > nCurrent + yCount - yCurrent:
                minPenalty = nCurrent + yCount - yCurrent
                result = i + 1
        
        return result
```
