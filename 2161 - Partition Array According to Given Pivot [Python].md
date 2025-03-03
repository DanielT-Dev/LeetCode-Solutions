# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/partition-array-according-to-given-pivot/?envType=daily-question&envId=2025-03-03)
# My Solution: 
```python
class Solution:
    def pivotArray(self, nums: List[int], pivot: int) -> List[int]:
        
        left = []
        right = []
        counter = 0

        for x in nums:
            if x < pivot:
                left.append(x)
            if x > pivot:
                right.append(x)
            if x == pivot:
                counter += 1

        return left + [pivot] * counter + right
```
