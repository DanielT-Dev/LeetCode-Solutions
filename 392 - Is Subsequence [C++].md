# Problem Statement: [https://leetcode.com/problems/is-subsequence/description/](https://leetcode.com/problems/is-subsequence/description/)
# My Solution: 
```c
class Solution {
public:
    bool isSubsequence(string s, string t) {
        int is = 0, it = 0, ls = s.length(), lt = t.length();
        while(is < ls)
        {
            while(s[is] != t[it] && it < lt)
                it++;
            it++;
            if(it > lt)
                return false;

            is++;
        }

        return true;
    }
};
```
