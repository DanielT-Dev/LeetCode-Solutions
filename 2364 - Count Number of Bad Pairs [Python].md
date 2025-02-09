# Statement: [Link to Leetcode](https://leetcode.com/problems/count-number-of-bad-pairs/)
# Solution:
```python
class Solution:
    def countBadPairs(self, nums: List[int]) -> int:
        
        n = len(nums)

        # bad pairs = total pairs - good pairs
        # good pairs = nums[i] - i == nums[j] - j
        # total pairs = n * (n - 1) // 2

        d = {}

        for i in range(n):
            if nums[i] - i not in d:
                d[nums[i] - i] = 0

            d[nums[i] - i] += 1

        good_pairs = 0
        total_pairs = n * (n - 1) // 2

        for k in d.keys():

            if d[k] > 1:
                d[k] -= 1
                good_pairs += d[k] * (d[k] + 1) // 2

        return total_pairs - good_pairs
```
