# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/number-of-substrings-containing-all-three-characters/?envType=daily-question&envId=2025-03-11)
# My Solution: 
```python
class Solution:
    def numberOfSubstrings(self, s: str) -> int:
        
        n = len(s)
        previous = {'a': -1, 'b': -1, 'c': -1}
        total = 0

        for i in range(n):
            
            # Update previous index
            previous[s[i]] = i

            # Compute starting index
            m = min(previous.values())

            if not m < 0:
                total += m + 1
        
        return total
```
