# Problem Statement: 
# My Solution:
```
class Solution {
public:
    int lengthOfLastWord(string s) {
        int l = s.length(), a = 0, i = l-1;
        while(s[i] == ' ')
            i--;
        for(;i >= 0;i--)
        {
            if(s[i] == ' ')
                return a;
            else 
                a++;
        }
        return a;
    }
};
```
