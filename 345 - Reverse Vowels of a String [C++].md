# Problem Statement: [https://leetcode.com/problems/reverse-vowels-of-a-string/description/](https://leetcode.com/problems/reverse-vowels-of-a-string/description/)
# My Solution: 
```c
class Solution {
public:
    string reverseVowels(string s) {
        vector<int> p;
        for(int i = 0;i < s.length();i++)
            if(strchr("aeiouAEIOU", s[i]))
                p.push_back(i);
        for(int i = 0;i < p.size()/2;i++)
            swap(s[p[i]], s[p[p.size()-1-i]]);
        return s;
    }
};
```
