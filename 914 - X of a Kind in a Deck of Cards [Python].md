# Problem Statement: [https://leetcode.com/problems/x-of-a-kind-in-a-deck-of-cards/description/](https://leetcode.com/problems/x-of-a-kind-in-a-deck-of-cards/description/)
# My Solution: 
```python
class Solution:

    def gcd(self, x, y):
        while y != 0:
            t = x % y
            x = y
            y = t
        return x

    def hasGroupsSizeX(self, deck: List[int]) -> bool:
        
        # Time Complexity: O(n)
        # Space Complexity: O(n) for frequency dictionary 
        n = len(deck)
        f = {}

        # Compute frequency of each number in the array
        for x in deck:
            if x not in f:
                f[x] = 0
            f[x] += 1

        # Compute GCD for the array of frequencies
        candidate_gcd = list(f.values())[0]
        for k in f.keys():
            candidate_gcd = self.gcd(candidate_gcd, f[k])
        
        return True if candidate_gcd > 1 else False
```
