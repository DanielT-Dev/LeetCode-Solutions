# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-common-value/description/)
# My Solution: 
```python
class Solution:
    def getCommon(self, nums1: List[int], nums2: List[int]) -> int:
        
        n, m = len(nums1), len(nums2)

        i, j = 0, 0

        while i < n and j < m:

            if nums1[i] == nums2[j]:
                return nums1[i] 
            
            if nums2[j] > nums1[i]:
                i += 1
            else:
                j += 1
            
        return -1
```
