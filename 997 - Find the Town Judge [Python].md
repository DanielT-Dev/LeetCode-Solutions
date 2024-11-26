# Problem Statement: [https://leetcode.com/problems/find-the-town-judge/description/](https://leetcode.com/problems/find-the-town-judge/description/0
# My Solution: 
```py
class Solution:
    def findJudge(self, n: int, trust: List[List[int]]) -> int:

        res = -1
        degree_1 = [0] * (n + 1)
        degree_2 = [0] * (n + 1)

        for a, b in trust:

            degree_1[b] += 1
            degree_2[a] += 1

        for i in range(1, n + 1):
            if degree_1[i] == n - 1 and degree_2[i] == 0:
                res = i

        return res
```
