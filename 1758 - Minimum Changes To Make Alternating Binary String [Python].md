```py
class Solution:
    def minOperations(self, s: str) -> int:
        
        # Time Complexity: O(n) linear
        # Space Complexity: O(1) constant

        modelA = 0
        modelB = 0

        for i in range(len(s)):
            c = s[i]

            if i % 2 == 0:
                modelA += 1 if c == '1' else 0
                modelB += 1 if c == '0' else 0
            else:
                modelA += 1 if c == '0' else 0
                modelB += 1 if c == '1' else 0

        return min(modelA, modelB)
```
