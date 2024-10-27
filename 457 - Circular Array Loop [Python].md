# Problem Statement: [https://leetcode.com/problems/circular-array-loop/description/](https://leetcode.com/problems/circular-array-loop/description/)
# My Solution: 
```
class Solution:
    def circularArrayLoop(self, nums: List[int]) -> bool:
        visited = set()

        l = len(nums)

        for i in range(l):
            if i not in visited:
                local = set()

                while True:
                    if i in local:
                        return True
                    if i in visited: 
                        break
                    
                    local.add(i)
                    visited.add(i)

                    prev = i
                    i = (i + nums[i]) % l

                    if prev == i or (nums[i] > 0) != (nums[prev] > 0):
                        break
        
        return False
        
```
