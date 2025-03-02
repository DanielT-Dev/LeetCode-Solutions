# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/merge-two-2d-arrays-by-summing-values/description/?envType=daily-question&envId=2025-03-02)
# My Solution: 
```python
class Solution:
    def mergeArrays(self, nums1: List[List[int]], nums2: List[List[int]]) -> List[List[int]]:
        
        d = {}
        result = []

        for k, v in nums1:

            if k not in d:
                d[k] = 0

            d[k] += v

        for k, v in nums2:

            if k not in d:
                d[k] = 0
            
            d[k] += v

        for k in sorted(d.keys()):
            result.append([k, d[k]])

        return result

```
