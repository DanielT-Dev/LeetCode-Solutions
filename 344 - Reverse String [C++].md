# Problem Statement: [https://leetcode.com/problems/reverse-string/description/](https://leetcode.com/problems/reverse-string/description/)
# My Solution: 
```c
class Solution {
public:
    void reverseString(vector<char>& s) {
        int l = s.size();
        for(int i = 0;i < l/2;i++)
            swap(s[i], s[l-1-i]);
    }
};
```
