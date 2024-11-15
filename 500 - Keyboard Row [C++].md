# Problem Statement: [https://leetcode.com/problems/keyboard-row/description/](https://leetcode.com/problems/keyboard-row/description/)
# My Solution: 
```c
class Solution {
public:
    vector<string> findWords(vector<string>& words) {
        vector<string> ans;
        char r1[] = "qwertyuiop";
        char r2[] = "asdfghjkl";
        char r3[] = "zxcvbnm";
        for(auto i : words)
        {
            bool p1 = true;
            bool p2 = true;
            bool p3 = true;
            for(auto c : i)
                if(strchr(r1, tolower(c)) == NULL)
                    p1 = false;
            for(auto c : i)
                if(strchr(r2, tolower(c)) == NULL)
                    p2 = false;
            for(auto c : i)
                if(strchr(r3, tolower(c)) == NULL)
                    p3 = false;
            if(p1 == true || p2 == true || p3 == true)
                ans.push_back(i);
        }
        return ans;
    }
};
```
