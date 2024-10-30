# Problem Statement: [https://leetcode.com/problems/count-sorted-vowel-strings/description/](https://leetcode.com/problems/count-sorted-vowel-strings/description/)
# My Solution: 
```
class Solution:
    def countVowelStrings(self, n: int) -> int:
        dp = [1] * 5

        for i in range(0, n - 1):
            for j in range(1, 5):
                dp[j] += dp[j - 1]
        
        return sum(dp)
```
