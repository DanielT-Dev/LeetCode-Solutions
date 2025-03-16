# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/minimum-time-to-repair-cars/description/?envType=daily-question&envId=2025-03-16)
# My Solution: 
```python
class Solution:
    def repairCars(self, ranks: List[int], counter_cars: int) -> int:
        
        def test_guess(guess_minutes):

            total_cars_repaired = 0

            # Check if the mechanics can repair the required number of cars (or more)
            # Stop search early if possible
            # Linear Search - Time Complexity O(n)
            for rank in ranks:
                total_cars_repaired += int(math.sqrt(guess_minutes // rank))
                
                if total_cars_repaired >= counter_cars:
                    return True

            return False

        counter_mechanics = len(ranks)

        # Compute left and right boundaries 
        # (min and max number of minutes)
        left = 1
        right = max(ranks) * (counter_cars ** 2)

        # Binary Search - Time Complexity O(log n)
        while left <= right:

            mid = (left + right) // 2

            if test_guess(mid):
                right = mid - 1
            else:
                left = mid + 1

        return left

```
