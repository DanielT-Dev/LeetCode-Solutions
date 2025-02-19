# Statement: [Link to Leetcode](https://leetcode.com/problems/count-numbers-with-unique-digits/)
# Solution:
```python
class Solution:
    def countNumbersWithUniqueDigits(self, n: int) -> int:

        total = 0

        for i in range(1, n + 1):
            counter = 1
            for j in range(i - 1):
                counter *= (9 - j) 
            total += 9 * counter

        return total + 1
```
