# Statement: [Link to Leetcode](https://leetcode.com/problems/word-pattern/description/)
# Solution:
```python
class Solution:
    def wordPattern(self, pattern: str, s: str) -> bool:
        
        s = s.split()

        n = len(s)

        if n != len(pattern):
            return False
        
        if len(set(s)) != len(set(pattern)):
            return False
            
        d = {}

        for i in range(n):

            if pattern[i] not in d:
                d[pattern[i]] = s[i]
            else:
                if s[i] != d[pattern[i]]:
                    return False


        return True
```
