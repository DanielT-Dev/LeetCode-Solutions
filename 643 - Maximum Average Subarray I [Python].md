# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-average-subarray-i/description/)
# My Solution: 
```python
class Solution:
    def findMaxAverage(self, nums: List[int], k: int) -> float:
        
        n = len(nums)

        result = float('-inf')

        if k == n:
            return float(sum(nums)) / k

        prefix_sum = [0] * n

        prefix_sum[0] = nums[0]

        for i in range(1, n):
            prefix_sum[i] = prefix_sum[i - 1] + nums[i]
        
        for i in range(k - 1, n):
            
            aux = prefix_sum[i] + nums[i - k + 1]
            aux -= prefix_sum[i - k + 1]

            result = max(float(aux), result)
        
        return result / k
```
