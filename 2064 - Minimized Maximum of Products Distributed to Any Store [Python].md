# Problem Statement: [https://leetcode.com/problems/minimized-maximum-of-products-distributed-to-any-store/description/](https://leetcode.com/problems/minimized-maximum-of-products-distributed-to-any-store/description/)
# My Solution: 
```py
class Solution:
    def minimizedMaximum(self, n: int, quantities: List[int]) -> int:

        l = len(quantities)

        def verify(n, candidate):
        
            count = 0

            for quantity in quantities:
                # Replaced by the formula below for better efficency: 
                #count += (quantity // candidate) + (1 if quantity % candidate != 0 else 0)
                count += (quantity + candidate - 1) // candidate
           
            return count <= n

        left = 1
        right = max(quantities)

        result = -1

        while left <= right:
            mid = (left + right) // 2

            if verify(n, mid):
                result = mid
                right = mid - 1
            else:
                left = mid + 1

        return result


```
