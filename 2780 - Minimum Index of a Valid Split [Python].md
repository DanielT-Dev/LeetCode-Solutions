# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-index-of-a-valid-split/?envType=daily-question&envId=2025-03-27)
# My Solution: 
```python
class Solution:
    def minimumIndex(self, nums: List[int]) -> int:
        
        n = len(nums)

        candidate, freq = Counter(nums).most_common(1)[0]

        current_freq = 0

        # Try all indexes
        # Time Complexity: O(n) - linear
        i = 0
        while i < n:
            if nums[i] == candidate:
                current_freq += 1

            # Check if current index is valid for splitting the array
            # Time Complexity: O(1) - constant
            if current_freq > (i + 1) // 2 and (freq - current_freq) > (n - (i + 1)) // 2:
                return i

            i += 1

        # In case no valid split exists
        return -1
```
