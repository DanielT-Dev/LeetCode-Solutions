# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-palindromic-substring/description/)
# My Solution: 
```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        # TC: O(n * l) where l is the length of the longest plaindromic substring
        # SC: O(1)
        
        n = len(s)
        result = ""

        for i in range(n):
            # Pick this index as the center of the palindromic substring
            left = i - 1
            right = i + 1

            # Expand the plaindromic substring as much as possible
            while left >= 0 and right < n and s[left] == s[right]:
                left -= 1
                right += 1

            if right - left - 1 > len(result):
                result = str(s[left + 1:right])

        for i in range(1, n):
            if s[i - 1] == s[i]:
                print(i, "DA")
                # Pick i and i - 1 as the center of the palindromic substring
                left = i - 2
                right = i + 1

                # Expand the plaindromic substring as much as possible
                while left >= 0 and right < n and s[left] == s[right]:
                    left -= 1
                    right += 1

                if right - left - 1 > len(result):
                    result = str(s[left + 1:right])

        return result
```
