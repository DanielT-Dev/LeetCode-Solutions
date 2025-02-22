# Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-sum-with-exactly-k-elements/)
# Solution:
```python
class Solution:
    def maximizeSum(self, nums: List[int], k: int) -> int:
        
        return k * max(nums) + (k - 1) * k // 2
```
