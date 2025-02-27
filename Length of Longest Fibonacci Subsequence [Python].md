# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/length-of-longest-fibonacci-subsequence/submissions/1557252303/?envType=daily-question&envId=2025-02-27)
# My Solution: 
```python
class Solution:
    def lenLongestFibSubseq(self, arr: List[int]) -> int:
        
        seen = set()

        for x in arr:
            seen.add(x)

        n = len(arr)
        result = 0

        for i in range(n):
            for j in range(i + 1, n):

                x = arr[i]
                y = arr[j]
                z = x + y
                length = 2

                while z in seen:
                    length += 1
                    x = y
                    y = z
                    z = x + y

                if length >= 3:
                    result = max(result, length)

        return result
```
