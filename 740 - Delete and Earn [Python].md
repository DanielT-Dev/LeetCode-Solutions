# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/delete-and-earn/description/?envType=study-plan-v2&envId=dynamic-programming)
# My Solution: 
```python
class Solution:


    def deleteAndEarn(self, nums: List[int]) -> int:

        # Using bottom-up dynammic programming
        # TC: O(n * log n) due to sorting
        # SC: O(u) where u is the count of the unique elements in the array

        if not nums:
            return 0

        frequency = Counter(nums)
        unique = sorted(frequency.keys())
        n = len(unique)

        take, skip = 0, 0

        for i in range(n):
            # element_points = element_value * element_frequency
            points = unique[i] * frequency[unique[i]]

            if i > 0 and unique[i] == unique[i - 1] + 1:
                take, skip = skip + points, max(skip, take)
            else:
                take, skip = max(skip, take) + points, max(skip, take)

        return max(take, skip)
```
