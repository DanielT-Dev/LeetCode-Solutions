# Problem Statement: [https://leetcode.com/problems/power-of-two/description/](https://leetcode.com/problems/power-of-two/description/)
# My Solution: 
```c
class Solution {
public:
    bool isPowerOfTwo(int n) {
        if(n <= 0)
            return false;
        while(n != 1)
        {
            if((n%10)%2 == 1)
                return false;
            n /= 2;
        }
        return true;
    }
};
```
