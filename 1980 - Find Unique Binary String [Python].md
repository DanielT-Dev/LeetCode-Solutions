# Statement: [Link to Leetcode](https://leetcode.com/problems/find-unique-binary-string/description/?envType=daily-question&envId=2025-02-20)
# Solution:
```python
class Solution:
    def findDifferentBinaryString(self, nums: List[str]) -> str:
        
        n = len(nums)
        candidate = []
        result = ""

        def backtracking(i):
            nonlocal result

            if i == n:
                if "".join(candidate) not in nums:
                    result = "".join(candidate)
                return

            candidate.append("0")
            if result == "":
                backtracking(i + 1)
            candidate.pop()

            candidate.append("1")
            if result == "":
                backtracking(i + 1)
            candidate.pop()

        backtracking(0)

        return result
```
