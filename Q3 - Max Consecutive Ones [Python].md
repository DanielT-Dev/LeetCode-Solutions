# Problem Statement: [https://leetcode.com/problems/max-consecutive-ones/?envType=problem-list-v2&envId=dsa-linear-shoal-array-i](https://leetcode.com/problems/max-consecutive-ones/?envType=problem-list-v2&envId=dsa-linear-shoal-array-i)
# My Solution: 
```python
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        
        result = 0
        length = 0

        for num in nums:
            if num == 1:
                length += 1
            else:
                result = max(result, length)
                length = 0
        
        return max(result, length)
```
