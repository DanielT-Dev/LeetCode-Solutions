# Problem Statement: [Link to Leetcode](https://github.com/Devinterview-io/oop-interview-questions)
# My Solution: 
```python
class Solution:
    def isPalindrome(self, s: str) -> bool:

        new_string = ''
        
        for ch in s:
            if ch.isalnum():
                new_string += ch.lower()

        n = len(new_string)

        for i in range(n // 2):
            if new_string[i] != new_string[n - i - 1]:
                return False
        
        return True
```
