# Problem Statement: [https://leetcode.com/problems/circular-sentence/description/](https://leetcode.com/problems/circular-sentence/description/)
# My Solution: 
```
class Solution:
    def isCircularSentence(self, sentence: str) -> bool:
        p = " "

        words = sentence.split()

        for w in words:

            if p == " ":
                p = w[-1]
                continue

            if p != w[0]:
                return False
            
            p = w[-1]
            
        
        return p == words[0][0]
```
