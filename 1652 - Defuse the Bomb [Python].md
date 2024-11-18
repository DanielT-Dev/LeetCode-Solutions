# Problem Statement: [https://leetcode.com/problems/defuse-the-bomb/description/](https://leetcode.com/problems/defuse-the-bomb/description/)
# My Solution: 
```py
class Solution:
    def decrypt(self, code: List[int], k: int) -> List[int]:

        l = len(code)

        if k == 0:
            return [0] * l

        partial_sums = [0] * l * 2

        partial_sums[0] = code[0]

        for i in range(1, l):
            partial_sums[i] = partial_sums[i - 1] + code[i]
        for i in range(l):
            partial_sums[i + l] = partial_sums[i + l - 1] + code[i]

        if abs(k) > l:
            k %= l

        if k > 0:
            for i in range(l):
                code[i] = partial_sums[i + k] - partial_sums[i]
        else:
            for i in range(l - 1, -1, -1):
                code[i] = partial_sums[i + l - 1] - partial_sums[i + l + k - 1]

        return code
```
