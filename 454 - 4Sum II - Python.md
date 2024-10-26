# Problem Statement: 
# [https://leetcode.com/problems/4sum-ii/](https://leetcode.com/problems/4sum-ii/)
# My code:
```
class Solution:
    def fourSumCount(self, nums1: List[int], nums2: List[int], nums3: List[int], nums4: List[int]) -> int:

        n = len(nums1)
        hashmap1 = {}
        hashmap2 = {}

        for i in range(n):
            for j in range(n):
                s = nums1[i] + nums2[j]

                if s not in hashmap1:
                    hashmap1[s] = 1
                else:
                    hashmap1[s] += 1
        
        for i in range(n):
            for j in range(n):
                s = nums3[i] + nums4[j]

                if s not in hashmap2:
                    hashmap2[s] = 1
                else:
                    hashmap2[s] += 1

        counter = 0

        for s in hashmap1:
            if -s in hashmap2:
                counter += hashmap1[s] * hashmap2[-s]
        
        return counter

        
```
