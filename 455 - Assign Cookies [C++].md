# Problem Statement: [https://leetcode.com/problems/assign-cookies/description/](https://leetcode.com/problems/assign-cookies/description/)
# My Solution: 
```c
class Solution {
public:
    int findContentChildren(vector<int>& g, vector<int>& s) {
        sort(g.begin(), g.end());
        sort(s.begin(), s.end());

        int i = 0, j = 0, gl = g.size(), sl = s.size();
        
        while(i < gl && j < sl)
        {
            if(g[i] <= s[j])
            {
                i++;
                j++;
            }
            else 
                j++;
        }

        return i;
    }
};
```
