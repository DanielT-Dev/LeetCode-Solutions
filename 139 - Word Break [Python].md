# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/word-break/)
# My Solution: 
```python
class Solution:
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:
        
        n = len(s)

        wordDict = set(wordDict)

        dp = [False] * (n + 1)

        dp[0] = True

        for i in range(1, n + 1):
            for j in range(i):

                if dp[j] and s[j:i] in wordDict:

                    dp[i] = True

                    break

        return dp[n]            
```
