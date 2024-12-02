# Problem Statement: [https://leetcode.com/problems/check-if-a-word-occurs-as-a-prefix-of-any-word-in-a-sentence/description/](https://leetcode.com/problems/check-if-a-word-occurs-as-a-prefix-of-any-word-in-a-sentence/description/)
# My Solution: 
```py
class Solution:
    def isPrefixOfWord(self, sentence: str, prefix: str) -> int:
        for index, word in enumerate(sentence.split(), start=1):
            if word.startswith(prefix):
                return index
        return -1

```
