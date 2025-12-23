# Problem Statement: [https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/?envType=problem-list-v2&envId=dsa-linear-shoal-array-ii](https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/?envType=problem-list-v2&envId=dsa-linear-shoal-array-ii)
# My Solution: 
```python
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        
        n = len(nums)
        result = [0] * n

        for i in range(n):
            for j in range(n):
                if nums[j] < nums[i]:
                    result[i] += 1
        
        return result
```
