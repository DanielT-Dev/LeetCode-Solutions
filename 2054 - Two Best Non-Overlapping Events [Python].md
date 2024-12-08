# Problem Statement: [https://leetcode.com/problems/two-best-non-overlapping-events/description/](https://leetcode.com/problems/two-best-non-overlapping-events/description/)
# My Solution: 
```py
class Solution:
    def maxTwoEvents(self, events: List[List[int]]) -> int:
        
        # Sort events by end time
        events.sort(key=lambda x: x[1])

        # Store maximum value of events seen so far
        max_value = 0
        result = 0

        # Create a list to store the maximum value until each event ends
        max_until = []
        end_times = []

        for start, end, value in events:

            #Use binary search to find the latest non-overlapping event
            index = bisect.bisect_left(end_times, start) - 1
            max_previous = max_until[index] if index >= 0 else 0

            # Update result with the sum of current event value and maximum non-overlapping value
            result = max(result, value + max_previous)

            # Update maximum value seen so far
            max_value = max(max_value, value)
            max_until.append(max_value)
            end_times.append(end)

        return result
```
