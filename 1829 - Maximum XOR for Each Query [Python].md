# Problem Statement: [https://leetcode.com/problems/maximum-xor-for-each-query/](https://leetcode.com/problems/maximum-xor-for-each-query/)
# My Solution: 
```py
class Solution:
    def getMaximumXor(self, nums: List[int], maximumBit: int) -> List[int]:
        
        s = None
        result = []

        for n in nums:
            if s == None:
                s = n
            else:
                s ^= n

            result.append(s ^ ((1 << maximumBit) - 1))
        
        result.reverse()

        return result
```
