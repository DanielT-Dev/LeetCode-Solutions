# Problem Statement: [https://leetcode.com/problems/valid-palindrome/description/](https://leetcode.com/problems/valid-palindrome/description/)
# My Solution: 
```
class Solution {
public:
    bool isPalindrome(string s) {
        string rs = "";

        for(auto i : s)
            if(isalnum(i))
                rs += tolower(i);

        int l = rs.length();
        for(int i = 0;i < l;i++)
            if(rs[i] != rs[l-i-1])
                return false;
        return true;
    }
};
```
