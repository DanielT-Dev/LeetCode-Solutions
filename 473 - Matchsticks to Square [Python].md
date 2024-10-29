# Problem Statement: [https://leetcode.com/problems/matchsticks-to-square/](https://leetcode.com/problems/matchsticks-to-square/)
# My Solution: 
```
class Solution:
    def makesquare(self, matchsticks: List[int]) -> bool:
        
        n = len(matchsticks)

        # If the sum of all matchsticks is X
        # Then in order to build a square using the matchsticks each of the 4 sides must be exactly of length X / 4
        # It is impossible to build a square with sides having less than X / 4 because that would imply not using all of the sticks
        # It is also obviously impossible to build a square with sides having more than X / 4
        s = sum(matchsticks)

        if s % 4 != 0:
            return False

        target = sum(matchsticks) // 4

        # [!!!] Sorting the matchsticks in descending order will cause the recursion tree to have less nodes since some of the possibilities will fail faster
        # Example: 
        # If (2, 3, 4, 5) fails
        # Then trying (2, 3, 4, 3 + 2) is guaranteed to fail too
        # In the same way (2, 3, 4, 2 + 3), (2, 3, 2 + 2, 5), (2, 0 + 3, 4, 5), (0 + 2, 3, 4, 5) are guaranteed to fail
        matchsticks.sort(reverse=True)

        # We will solve using Top-Down Dynammic Programming (Memoization)

        dp = {}

        def solve(step, sides):

            if step == n:
                return sides[0] == sides[1] == sides[2] == sides[3]

            # Sort the sides in ascending order because we do not want to waste time to consider permutations of the set represented by the 4 sides
            sorted_sides = sorted(sides)

            # Convert to tuple for indexing
            sides_tuple = (
                sorted_sides[0], 
                sorted_sides[1], 
                sorted_sides[2], 
                sorted_sides[3]
            )

            # Memoization
            if sides_tuple in dp:
                return dp[sides_tuple]

            # Assume the result of this subproblem is False
            dp[sides_tuple] = False

            for i in range(4):
                if sides[i] + matchsticks[step] <= target:

                    sides[i] += matchsticks[step]

                    dp[sides_tuple] |= solve(step + 1, sides)

                    sides[i] -= matchsticks[step]

            return dp[sides_tuple]
        
        return solve(0, [0] * 4)
```
