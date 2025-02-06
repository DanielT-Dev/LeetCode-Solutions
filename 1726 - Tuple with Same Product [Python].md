# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/tuple-with-same-product/description/?envType=daily-question&envId=2025-02-06)
# My Solution: 
```python
class Solution:
    def tupleSameProduct(self, nums: List[int]) -> int:
        
        n = len(nums)

        d = {}

        total = 0

        for i in range(n):
            for j in range(i + 1, n):
                
                if nums[i] * nums[j] not in d:
                    d[nums[i] * nums[j]] = 0
                
                d[nums[i] * nums[j]] += 1

        for k in d.keys():

            if d[k] == 1:
                continue

            t = d[k] - 1

            total += t * (t + 1) // 2

        return 8 * total
```
