# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/alternating-groups-ii/description/?envType=daily-question&envId=2025-03-09)
# My Solution: 
```python
class Solution:
    def numberOfAlternatingGroups(self, colors: List[int], k: int) -> int:
        
        n = len(colors)

        # Store counter of color switches in prefix sum array
        # We can use this prefix array to find how many alternating colors we have 
        # in a range [a, a + k - 1] in constant time complexity O(1)
        prefix = [0] * 2 * n

        # Build prefix sum
        for i in range(1, 2 * n):
            # Color switch
            if colors[i % n] != colors[i % n - 1]:
                prefix[i] = prefix[i - 1] + 1
            # No color switch
            else:
                prefix[i] = prefix[i - 1]

        left = 0
        right = k - 1
        result = 0

        while left < n:

            t = 1 if (colors[left] == colors[(left + 1) % n]) else 0

            if prefix[right] - prefix[left] - t == k - 1:
                result += 1

            left = left + 1
            right = right + 1
        
        return result
```
