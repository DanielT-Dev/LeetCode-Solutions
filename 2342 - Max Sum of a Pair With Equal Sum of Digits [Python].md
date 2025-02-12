# Statement: [Link to Leetcode](https://leetcode.com/problems/max-sum-of-a-pair-with-equal-sum-of-digits/description/?envType=daily-question&envId=2025-02-12)
# Solution:
```python
class Solution:
    def maximumSum(self, nums: List[int]) -> int:
        
        def sum_of_digits(x):
            c = x
            s = 0
            while c:
                s += c % 10
                c //= 10
            return s

        sums = [sum_of_digits(x) for x in nums]

        n = len(nums)

        d = {}

        for i in range(n):

            if sums[i] not in d:
                d[sums[i]] = [-1, -1]

            max1 = d[sums[i]][0]
            max2 = d[sums[i]][1]

            if nums[i] >= max1:
                d[sums[i]][0] = nums[i]
                d[sums[i]][1] = max1

            elif nums[i] > max2:
                d[sums[i]][1] = nums[i]

        result = -1

        for k in d.keys():

            if d[k][0] != -1 and d[k][1] != -1:
                result = max(result, d[k][0] + d[k][1])

        return result
```
