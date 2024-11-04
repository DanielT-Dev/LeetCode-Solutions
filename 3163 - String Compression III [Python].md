# Problem Statement: [https://leetcode.com/problems/string-compression-iii/description/](https://leetcode.com/problems/string-compression-iii/description/)
# My Solution: 
```
class Solution:
    def compressedString(self, word: str) -> str:
        word = list(word)

        p = None
        l = 0
        ans = ""

        for c in word:
            if p == c and l < 9:
                l += 1
            else:
                if l > 0:
                    ans += str(l)
                    ans += p

                l = 1

            p = c

        ans += str(l)
        ans += p

        return ans
```
