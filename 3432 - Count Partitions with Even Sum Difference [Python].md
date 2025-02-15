# Statement: [Link to Leetcode]()
# Solution:
```python
class Solution:
    def countPartitions(self, nums: List[int]) -> int:
        n = len(nums)
        total = sum(nums)
        if total % 2 == 0:
            return n - 1
        return 0
```
