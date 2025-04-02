# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-value-of-an-ordered-triplet-i/?envType=daily-question&envId=2025-04-02)
# My Solution: 
```python
class Solution:
    def maximumTripletValue(self, nums: List[int]) -> int:

        '''
        Find and store maximum element in the left and right sides
        Time complexity: O(n)

        Pick maximum value for the given formula using the previously computed
        left and right arrays
        Time complexisty: O(n)

        Final time complexity: O(n)
        '''
        
        n = len(nums)
        result = 0

        left = [0] * n

        for i in range(n):
            if i == 0:
                left[i] = nums[i]
            else:
                left[i] = max(left[i - 1] , nums[i])

        right = [0] * n

        for i in range(n):
            if i == 0:
                right[i] = nums[n - i - 1]
            else:
                right[i] = max(right[i - 1], nums[n - i - 1])

        for i in range(1, n - 1):
            result = max(result, (left[i - 1] - nums[i]) * right[n - i - 2])

        return result
```
