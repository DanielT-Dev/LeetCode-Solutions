# Problem Statement: [https://leetcode.com/problems/ones-and-zeroes/description/](https://leetcode.com/problems/ones-and-zeroes/description/)
# My Solution: 
```
class Solution:
    def findMaxForm(self, strs: List[str], m: int, n: int) -> int:
        l = len(strs)

        arr = []

        for s in strs:

            ones_counter = s.count('1')
            zeroes_counter = len(s) - ones_counter

            arr.append((ones_counter, zeroes_counter))

        # We will use DP method
        dp = {}

        # Sort strings in reverse order for Fail Faster approach
        # (this will help us avoid computing posibilities that we know will fail)
        arr.sort(reverse=True)
        
        def solve(step, ones_sum, zeroes_sum):
            # Stop conditions
            # [!!!] The order in which we write these conditions is important because:
            # conditions number 1, 2 and condition 3 are independent
            # that means they can happen at the same time
            # in this case, we put conditions 1, 2 before condition 3
            if ones_sum > n:
                return -1
            if zeroes_sum > m:
                return -1
            if step == l:
                return 0

            # Memorization stop
            if (step, ones_sum, zeroes_sum) in dp:
                return dp[(step, ones_sum, zeroes_sum)]

            current_string = arr[step]
            ones = current_string[0]
            zeroes = current_string[1]

            # Pick current string
            p1 = 1 + solve(
                step + 1, 
                ones_sum + ones, 
                zeroes_sum + zeroes
            )
            # Ignore current string
            p2 = solve(
                step + 1,
                ones_sum,
                zeroes_sum
            )

            # Save best posibility
            dp[(step, ones_sum, zeroes_sum)] = max(p1, p2)

            # Return best posibility for this sub-problem
            return dp[(step, ones_sum, zeroes_sum)]

        return solve(0, 0, 0)
```
