# Problem Statement: [https://leetcode.com/problems/most-common-word/](https://leetcode.com/problems/most-common-word/)
# My Solution: 
```python
class Solution:
    def mostCommonWord(self, paragraph: str, banned: List[str]) -> str:
         
        delimiters = "!?',;. "
        maximum = -1
        result = ''
        freq = {}
        clean = re.split(f"[{re.escape(delimiters)}]", paragraph)
        clean = [c.lower() for c in clean]

        for c in clean:
            if c == '':
                continue
            if c not in freq:
                freq[c] = 0
            freq[c] += 1
            if c not in banned:
                maximum = max(maximum, freq[c])
                if freq[c] == maximum:
                    result = c  

        return result
```
