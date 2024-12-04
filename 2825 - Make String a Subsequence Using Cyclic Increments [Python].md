# Problem Statement: [https://leetcode.com/problems/make-string-a-subsequence-using-cyclic-increments/description/](https://leetcode.com/problems/make-string-a-subsequence-using-cyclic-increments/description/)
# My Solution: 
```py
class Solution:
    def canMakeSubsequence(self, str1: str, str2: str) -> bool:
        m = len(str1)
        n = len(str2)
        i = j = 0

        def next_character(x):
            return chr((ord(x) - ord('a') + 1) % 26 + ord('a'))

        while i < m and j < n:
            if str1[i] == str2[j] or next_character(str1[i]) == str2[j]:
                j += 1
            i += 1

        return j == n

```
