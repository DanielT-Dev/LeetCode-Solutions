# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/special-array-i/?envType=daily-question&envId=2025-02-01)
# My Solution: 
```python
class Solution:
    def isArraySpecial(self, nums: List[int]) -> bool:
        
        n = len(nums)

        def parity(number):

            return number % 2
        
        if n == 1:

            return True
        
        if n == 2:

            return parity(nums[0]) != parity(nums[1])

        
        for i in range(1, n - 1):

            if parity(nums[i]):
                if parity(nums[i + 1]) or parity(nums[i - 1]):
                    return False
            if not parity(nums[i]):
                if not (parity(nums[i + 1]) and parity(nums[i - 1])):
                    return False
                    

        return True 
```
