# Statement: [Link to Leetcode](https://leetcode.com/problems/find-minimum-operations-to-make-all-elements-divisible-by-three/description/)
# Solution:
```python
class Solution:
    def minimumOperations(self, nums: List[int]) -> int:
        
        return sum([1 for x in nums if x % 3 != 0])
```
