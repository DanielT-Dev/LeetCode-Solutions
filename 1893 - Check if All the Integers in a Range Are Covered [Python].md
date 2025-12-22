# Problem Statement: [https://leetcode.com/problems/check-if-all-the-integers-in-a-range-are-covered/](https://leetcode.com/problems/check-if-all-the-integers-in-a-range-are-covered/)
# My Solution: 
```python
class Solution:
    def isCovered(self, ranges: List[List[int]], left: int, right: int) -> bool:
        
        # Time Complexity: O(n * m) where n is the total sum of ranges and m is the range of numbers to check

        # Declare frequency array
        freq = [False] * 55

        counter = 0

        # Take each given range
        for a, b in ranges:
            # Update frequency of present elements
            for i in range(a, b + 1):
                if freq[i] == False and i >= left and i <= right:
                    freq[i] = True
                    counter += 1

        return counter == right - left + 1
                
```
