# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-recolors-to-get-k-consecutive-black-blocks/?envType=daily-question&envId=2025-03-08)
# My Solution: 
```python
class Solution:
    def minimumRecolors(self, blocks: str, k: int) -> int:
        
        n = len(blocks)
        counter = 0
        result = float("inf")

        for i in range(n):
            if i - k >= 0 and blocks[i - k] == 'B':
                counter -= 1
            if blocks[i] == 'B':
                counter += 1
            result = min(result, k - counter)

        return result
```
