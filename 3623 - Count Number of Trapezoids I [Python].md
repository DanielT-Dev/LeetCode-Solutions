# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/count-number-of-trapezoids-i/submissions/1845336588/?envType=daily-question&envId=2025-12-02)
# My Solution: 
```python
class Solution:
    def countTrapezoids(self, points: List[List[int]]) -> int:
        # Time complexity: O(n) linear where n is the number of points
        # Space complexity: additional O(m) for dictionary where m is the number of distinct y-axis
        # coordinates
        # For each horizontal line (x axis included):
        #
        # The number of ways in which we can choose 2 points from
        # the line is: n * (n - 1) / 2
        #
        # The total number of horizontal trapezoids that can be formed
        # is the total number of ways in which we can choose 2 horizontal lines

        MOD = 1000000000 + 7

        # Store number of points on the same horizontal line in a 
        # dictonary data strcuture: (y, c) where y is the coordinate and c
        # the total count of points on the line 
        count = {}

        for [x, y] in points:

            if y not in count:
                count[y] = 0

            count[y] += 1

        # Compute L1 + L2 + L3 + ... + Ln sum
        # where Li is the number of ways in which we can form a straight line
        # with the points of the ith line
        s = 0

        for y in count.keys():
            s += count[y] * (count[y] - 1) // 2
            s %= MOD

        # Result = 
        # L1 * (L2 + ... + Ln) + 
        # L2 * (L3 + ... + Ln) + 
        # L3 * (L4 + ... + Ln) + 
        # .....
        # => remove Li from the sum at each step
        result = 0
        for y in count.keys():
            ways = count[y] * (count[y] - 1) // 2
            s -= ways
            result += ways * s
            result %= MOD

        return int(result)       
```
