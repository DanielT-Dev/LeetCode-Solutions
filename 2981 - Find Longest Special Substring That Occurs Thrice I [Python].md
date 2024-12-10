# Problem Statement: [https://leetcode.com/problems/find-longest-special-substring-that-occurs-thrice-i/description/](https://leetcode.com/problems/find-longest-special-substring-that-occurs-thrice-i/description/)
# My Solution: 
```py
class Solution:
    def maximumLength(self, s: str) -> int:
        
        n = len(s)

        # Store prefix sums in list of tuples (character, length)
        prefix_sums = []

        f = 1
        for i in range(1, n):
            if s[i - 1] == s[i]:
                f += 1
            else:
                prefix_sums.append((s[i - 1], f))
                f = 1

        # Consider last substring
        prefix_sums.append((s[n - 1], f))

        # Test if candidate is valid
        def test(prefix_sums, candidate):

            d = {}

            for c, l in prefix_sums:

                if c not in d:
                    d[c] = 0                

                if l - candidate >= 0:
                    d[c] += l - candidate + 1
                
                if d[c] >= 3:
                    return True
            
            return False

        # Binary Search maximum length special substring
        left = 1
        right = n
        answer = -1

        while left <= right:

            mid = (left + right) // 2

            test_result = test(prefix_sums, mid)

            if test_result == True:
                answer = mid
                left = mid + 1
            else:
                right = mid - 1

        return answer
```
