# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/find-missing-and-repeated-values/description/?envType=daily-question&envId=2025-03-06)
# My Solution: 
```python
class Solution:
    def findMissingAndRepeatedValues(self, grid: List[List[int]]) -> List[int]:
        n = len(grid)
        n_squared = n * n
        
        expected_sum = n_squared * (n_squared + 1) // 2
        expected_sum_squares = n_squared * (n_squared + 1) * (2 * n_squared + 1) // 6
        
        actual_sum = 0
        actual_sum_squares = 0
        
        for i in range(n):
            for j in range(n):
                actual_sum += grid[i][j]
                actual_sum_squares += grid[i][j] * grid[i][j]

        # a - b
        diff_sum = actual_sum - expected_sum

        # a² - b²
        diff_sum_squares = actual_sum_squares - expected_sum_squares
        
        # a + b = (a² - b²) / (a - b)
        sum_a_b = diff_sum_squares // diff_sum
        
        # Now we can find a and b
        a = (sum_a_b + diff_sum) // 2
        b = (sum_a_b - diff_sum) // 2
        
        return [a, b]
```
