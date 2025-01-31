# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/maximum-subarray-with-equal-products/description/?envType=problem-list-v2&envId=sliding-window)
# My Solution: 
```python
class Solution:
    def maxLength(self, nums: List[int]) -> int:
        
        def get_gcd(a, b):

            while b:
                r = a % b
                a = b
                b = r
            
            return a

        def get_lcm(a, b):
            return a * b // get_gcd(a, b)

        n = len(nums)

        result = 1

        for start in range(n):

            prod = nums[start]
            gcd = nums[start]
            lcm = nums[start]

            for i in range(start + 1, n):

                prod = prod * nums[i]

                gcd = get_gcd(gcd, nums[i])

                lcm = get_lcm(lcm, nums[i])

                if prod == lcm * gcd:
                    result = max(result, i - start + 1)
        
        return result
```
