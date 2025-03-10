# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/count-of-substrings-containing-every-vowel-and-k-consonants-ii/?envType=daily-question&envId=2025-03-10)
# My Solution: 
```python
class Solution:
    def countOfSubstrings(self, word: str, k: int) -> int:
        res = cons = left = cur = 0
        freq = defaultdict(int)
        vowel = 'aeiou'

        for ch in word:
            # count vowel frequency and number of consonants in the current window
            if ch in vowel:
                freq[ch] += 1
            else: 
                cons += 1
                # reset number of valid substring found in the current window since now it is no more valid
                cur = 0 

            # shrink until we have the right amount of consonants
            while cons > k:
                if word[left] not in vowel:
                    cons -= 1
                elif freq[word[left]] == 1:
                    del freq[word[left]]
                else:
                    freq[word[left]] -= 1
                left += 1

            # if we have the right amount of consonants and vowels, shrink current window as much as possible
            # each step is a probable substring if we keep finding vowels on the right
            while len(freq) == 5 and cons == k:
                cur += 1
                if word[left] not in vowel:
                    cons -= 1
                elif freq[word[left]] == 1:
                    del freq[word[left]]
                else:
                    freq[word[left]] -= 1
                left += 1
            res += cur # sum the overall number of substring in the current window
        return res

            
```
