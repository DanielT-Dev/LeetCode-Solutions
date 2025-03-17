# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/divide-array-into-equal-pairs/description/?envType=daily-question&envId=2025-03-17)
# My Solution: 
```python
class Solution:
    def divideArray(self, nums: List[int]) -> bool:
        
        d = Counter(nums)
        
        for v in d.values():
            if v % 2 == 1:
                return False
        
        return True
```
