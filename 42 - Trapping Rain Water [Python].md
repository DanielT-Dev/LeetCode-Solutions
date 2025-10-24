# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/trapping-rain-water/description/)
# My Solution: 
```python
class Solution:
    def trap(self, height: List[int]) -> int:
        # Using 2 pointers
        # TC: O(n) linear
        # SC: O(1) no auxiliary space needed

        n = len(height)
        left, right = 0, n - 1
        max_left, max_right = 0, 0
        total = 0

        while left < right:
            if height[left] <= height[right]:
                # Update decisive boundary on the left
                if height[left] > max_left:
                    max_left = height[left]
                else:
                    # Add water
                    total += height[left] - max_left

                # Advance pointer
                left += 1
            else:
                # Update decisive boundary on the right
                if height[right] > max_right:
                    max_right = height[right]
                else:
                    # Add water
                    total += height[right] - max_right

                # Advance pointer
                right -= 1

        return -total         
```
