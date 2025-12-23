# Problem Statement: [https://leetcode.com/problems/shuffle-the-array/description/?envType=problem-list-v2&envId=dsa-linear-shoal-array-i](https://leetcode.com/problems/shuffle-the-array/description/?envType=problem-list-v2&envId=dsa-linear-shoal-array-i)
# My Solution: 
```python
class Solution:
    def shuffle(self, nums: List[int], n: int) -> List[int]:
        
        return [nums[i // 2] if i % 2 == 0 else nums[i // 2 + n] for i in range(2 * n)]
```
