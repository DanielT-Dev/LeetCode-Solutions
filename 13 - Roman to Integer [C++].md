# Problem Statement: [https://leetcode.com/problems/roman-to-integer/description/](https://leetcode.com/problems/roman-to-integer/description/)
# My Solution:
```
class Solution {
public:
    int romanToInt(string s) {
        int value = 0;
        int n = s.size();
        for(int i = n-1;i >= 0;i--)
            if(s[i] == 'I')
                value += 1;
            else if(s[i] == 'V')
            {
                if(i-1 >= 0 && s[i-1] == 'I')
                {
                    value += 4;
                    i--;
                }
                else 
                    value += 5;
            }
            else if(s[i] == 'X')
            {
                if(i-1 >= 0 && s[i-1] == 'I')
                {
                    value += 9;
                    i--;
                }
                else 
                    value += 10;
            }
            else if(s[i] == 'L')
            {
                if(i-1 >= 0 && s[i-1] == 'X')
                {
                    value += 40;
                    i--;
                }
                else 
                    value += 50;
            }
            else if(s[i] == 'C')
            {
                if(i-1 >= 0 && s[i-1] == 'X')
                {
                    value += 90;
                    i--;
                }
                else 
                    value += 100;
            }
            else if(s[i] == 'D')
            {
                if(i-1 >= 0 && s[i-1] == 'C')
                {
                    value += 400;
                    i--;
                }
                else 
                    value += 500;
            }
            else if(s[i] == 'M')
            {
                if(i-1 >= 0 && s[i-1] == 'C')
                {
                    value += 900;
                    i--;
                }
                else 
                    value += 1000;
            }
        return value;
    }
};
```
