# Problem Statement: [https://leetcode.com/problems/continuous-subarrays/](https://leetcode.com/problems/continuous-subarrays/)
# My Solution: 
```py
class Solution:
    def continuousSubarrays(self, nums: List[int]) -> int:
        
        n = len(nums)
        min_dq = deque()
        max_dq = deque()
        l = 0
        result = 0

        for r in range(n):
            while min_dq and nums[min_dq[-1]] >= nums[r]:
                min_dq.pop()
            while max_dq and nums[max_dq[-1]] <= nums[r]:
                max_dq.pop()
            min_dq.append(r)
            max_dq.append(r)

            while nums[max_dq[0]] - nums[min_dq[0]] > 2:
                l += 1
                if min_dq[0] < l:
                    min_dq.popleft()
                if max_dq[0] < l:
                    max_dq.popleft()

            result += r - l + 1

        return result
```
