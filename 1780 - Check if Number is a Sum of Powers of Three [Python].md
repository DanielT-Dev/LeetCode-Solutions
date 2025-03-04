# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/check-if-number-is-a-sum-of-powers-of-three/?envType=daily-question&envId=2025-03-04)
# My Solution: 
```python
class Solution:
    def checkPowersOfThree(self, n: int) -> bool:
        
        while n != 1:
            if n % 3 == 2:
                return False
            n //= 3

        return True
```
