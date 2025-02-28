# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/number-of-longest-increasing-subsequence/)
# My Solution: 
```python
class Solution:
    def findNumberOfLIS(self, nums: List[int]) -> int:
        
        """
        ----- x2 ----- x1 ---- y ------------

        ----- i2 ----- i2 ---- j ------------

        if x < y

        then dp[x] + 1 == dp[y]
             sum(sdp[x]) == sdp[y]
        """

        n = len(nums)

        dp = [1] * n
        sdp = [1] * n

        max_length = 1
        max_count = 1

        for j in range(n):

            y = nums[j]

            for i in range(j):

                x = nums[i]

                if x < y:

                    if dp[i] + 1 > dp[j]:
                        dp[j] = dp[i] + 1
                        sdp[j] = sdp[i]
                    elif dp[i] + 1 == dp[j]:
                        sdp[j] += sdp[i]

            if dp[j] > max_length:
                max_length = dp[j]
                max_count = sdp[j]
            elif dp[j] == max_length:
                max_count += sdp[j]

        if max_length == 1:
            return n

        return max_count

```
