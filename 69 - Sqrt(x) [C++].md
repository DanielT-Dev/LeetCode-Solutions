# Problem Statement: [https://leetcode.com/problems/sqrtx/description/](https://leetcode.com/problems/sqrtx/description/)
# My Solution: 
```
class Solution {
public:
    int mySqrt(int x) {
        long long int posible = 1;
        while(posible*posible <= x)
            posible++;
        return posible-1;
    }
};
```
