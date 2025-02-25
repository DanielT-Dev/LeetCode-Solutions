# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/number-of-sub-arrays-with-odd-sum/?envType=daily-question&envId=2025-02-25)
# My Solution: 
```python
class Solution:
    def numOfSubarrays(self, arr: List[int]) -> int:

        n = len(arr)

        even = odd = 0
        result = 0

        for i in range(n):

            # even + even = even
            # odd + even = odd

            # even + odd = odd
            # odd + odd = even

            even += 1

            if arr[i] % 2 == 1:

                even, odd = odd, even

            result = (result + odd) % 1000000007

        return result
```
