# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/check-if-one-string-swap-can-make-strings-equal/?envType=daily-question&envId=2025-02-05)
# My Solution: 
```python
class Solution:
    def areAlmostEqual(self, s1: str, s2: str) -> bool:
        
        n = len(s1)

        counter = 0

        for i in range(n):
            if s1[i] != s2[i]:
                counter += 1
        
        if counter == 0:
            return True
        if counter == 2:

            d1 = Counter(s1)
            d2 = Counter(s2)

            return d1 == d2
        else:
            return False
```
