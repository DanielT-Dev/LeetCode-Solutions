# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/vowels-game-in-a-string/)
# My Solution: 
```python
class Solution:
    def doesAliceWin(self, s: str) -> bool:

        return False if len([x for x in s if x in 'aeiou']) == 0 else True
```
