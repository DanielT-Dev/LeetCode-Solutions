# Problem Statement: [https://leetcode.com/problems/max-chunks-to-make-sorted/description/?envType=daily-question&envId=2024-12-19](https://leetcode.com/problems/max-chunks-to-make-sorted/description/?envType=daily-question&envId=2024-12-19)
# My Solution: 
```py
class Solution:
    def maxChunksToSorted(self, arr: List[int]) -> int:

        n = len(arr)
        maximum = 0
        counter = 0

        for i in range(n):
            maximum = max(maximum, arr[i])

            if i == maximum:
                counter += 1
                maximum = 0

        return counter
```
