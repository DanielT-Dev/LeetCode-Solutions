# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/count-total-number-of-colored-cells/description/?envType=daily-question&envId=2025-03-05)
# My Solution: 
```python
class Solution:
    def coloredCells(self, n: int) -> int:
        
        return 1 + 2 * n * (n - 1)

        """
        n = 0       1
        n = 1       1 * 4
        n = 2       2 * 4
        n = 3       3 * 4
        n = 4       4 * 4
        .....

        1 + 1 * 4 + 2 * 4 + 3 * 4 + 4 * 4 + ..... + n * 4

        1 + 4 * (1 + 2 + 3 + 4 + ... n)
        1 + 2 * n * (n + 1)
        """
```
