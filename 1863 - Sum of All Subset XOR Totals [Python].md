# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/sum-of-all-subset-xor-totals/description/?envType=daily-question&envId=2025-04-05)
# My Solution: 
```python
class Solution:
    def subsetXORSum(self, nums: List[int]) -> int:
        
        n = len(nums)

        def backtracking(i, xor_result):
            
            # Exit condition
            if not i < n:
                return xor_result

            # include
            result1 = backtracking(i + 1, nums[i] ^ xor_result)

            # exclude
            result2 = backtracking(i + 1, xor_result)

            return result1 + result2

        return backtracking(0, 0)
```
