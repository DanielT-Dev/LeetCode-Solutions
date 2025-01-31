# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-nice-substring/description/)
# My Solution: 
```python
class Solution:
    def longestNiceSubstring(self, s: str) -> str:
        
        def is_nice(x):

            x = set(x)

            for c in x:
                if c.lower() not in x or c.upper() not in x:
                    return False

            return True

        s = list(s)

        n = len(s)

        for length in range(n, 0, -1):

            x = deque()

            for i in range(length):
                x.append(s[i])

            if is_nice(x):
                return "".join(x)

            for i in range(length, n):

                x.popleft()

                x.append(s[i])

                if is_nice(x):
                    return "".join(x)

        return ""
```
