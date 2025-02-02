# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-substring-without-repeating-characters/description/)
# My Solution: 
```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        
        n = len(s)

        # Edge case
        if s == '':
            return 0
  
        # Store character frequency
        d = {}

        # Store start of substring
        start = 0

        result = 1

        for i in range(n):

            if s[i] not in d:
                d[s[i]] = 0

            # Update frequency
            d[s[i]] += 1

            # If frequency is greater than 1
            if d[s[i]] > 1:

                # Update result
                result = max(result, i - start)

                j = start
                
                # Remove characters from left untill the duplicate is removed
                while d[s[i]] > 1:
                    
                    d[s[j]] -= 1
                    j += 1

                # Update start position of the substring
                start = j

        result = max(result, n - start)
        
        return result
```
