# Problem Statement: [https://leetcode.com/problems/first-unique-character-in-a-string/description/](https://leetcode.com/problems/first-unique-character-in-a-string/description/)
# My Solution: 
```c
class Solution {
public:
    int firstUniqChar(string s) {
        map<char, int> m;
        for(auto i : s)
            m[i]++;
        int j = 0;
        for(auto i : s)
        {
            if(m[i] == 1)
                return j;
            j++;
        }
        return -1;
    }
};
```
