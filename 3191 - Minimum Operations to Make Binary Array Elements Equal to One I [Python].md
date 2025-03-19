# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-operations-to-make-binary-array-elements-equal-to-one-i/description/?envType=daily-question&envId=2025-03-19)
# My Solution: 
```python
class Solution:
    def minOperations(self, nums: List[int]) -> int:
        
        n = len(nums)
        counter = 0

        # Always keep all elements from left side set to 1
        # Simulate operations
        # O(n)
        for i in range(n):
            if nums[i] == 0:

                counter += 1

                if i + 1 < n:
                    nums[i + 1] = 1 - nums[i + 1]
                
                if i + 2 < n:
                    nums[i + 2] = 1 - nums[i + 2]

        # Final check
        if nums[n - 1] == 0 or nums[n - 2] == 0:
            return -1

        return counter
```
