# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/detect-capital/)
# My Solution: 
```python
class Solution:
    def detectCapitalUse(self, word: str) -> bool:
        return word==word.upper() or word==word.capitalize() or word==word.lower()
```
