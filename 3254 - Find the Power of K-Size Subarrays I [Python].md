# Problem Statement: [https://leetcode.com/problems/find-the-power-of-k-size-subarrays-i/description/](https://leetcode.com/problems/find-the-power-of-k-size-subarrays-i/description/)
# My Solution: 
```py
class Solution:
    def resultsArray(self, nums: List[int], k: int) -> List[int]:
        
        l = len(nums)

        count = 0

        result = []

        for i in range(1, k):
            if nums[i - 1] + 1 == nums[i]:
                count += 1
        
        for i in range(k, l):
            if count == k - 1:
                result.append(nums[i - 1])
            else:
                result.append(-1)
            
            if nums[i - k] + 1 == nums[i - k + 1]:
                count -= 1
            if nums[i - 1] + 1 == nums[i]:
                count += 1
        
        if count == k - 1:
            result.append(nums[l - 1])
        else:
            result.append(-1)

        return result


```
