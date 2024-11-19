# Problem Statement: [https://leetcode.com/problems/maximum-sum-of-distinct-subarrays-with-length-k/description/](https://leetcode.com/problems/maximum-sum-of-distinct-subarrays-with-length-k/description/)
# My Solution: 
```py
class Solution:
    def maximumSubarraySum(self, nums: List[int], k: int) -> int:
        
        l = len(nums)
        elements = set()
        s = 0
        answer = 0
        left = 0

        for right in range(l):

            current = nums[right]

            if current not in elements:
                s += current
                elements.add(current)

                if right - left + 1 == k:
                    answer = max(answer, s)

                    s -= nums[left]
                    elements.remove(nums[left])
                    left += 1
            else:
                while nums[left] != nums[right]:
                    s -= nums[left]
                    elements.remove(nums[left])
                    left += 1
                left += 1
        
        return answer
```
