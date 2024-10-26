# Problem Statement: [https://leetcode.com/problems/palindrome-number/description/](https://leetcode.com/problems/palindrome-number/description/)
# My Solution:
```
class Solution {
public:
    bool isPalindrome(int x) {
        if(x < 0)
            return false;
        long long int rx = 0, cx = x;
        while(x)
        {
            rx *= 10;
            rx += x%10;
            x /= 10;
        }
        return rx == cx;
    }
};
```
