# Problem Statement: [https://leetcode.com/problems/unique-number-of-occurrences/](https://leetcode.com/problems/unique-number-of-occurrences/)
# My Solution: 
```python
class Solution:
    def uniqueOccurrences(self, arr: List[int]) -> bool:

        # Time Complexity: O(n)

        freq = Counter(arr)
        seen = set()

        for key, value in freq.items():
            if value in seen:
                return False
            seen.add(value)

        return True
```
