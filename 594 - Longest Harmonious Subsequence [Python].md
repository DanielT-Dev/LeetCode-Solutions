# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/longest-harmonious-subsequence/description/)
# My Solution: 
```python
class Solution:
    def findLHS(self, nums: List[int]) -> int:
        
        nums.sort()
        result = 0
        freq = Counter(nums)

        for i in range(len(nums) - 1):
            if nums[i + 1] - nums[i] == 1:
                result = max(result, freq[nums[i + 1]] + freq[nums[i]])
        
        return result
```
