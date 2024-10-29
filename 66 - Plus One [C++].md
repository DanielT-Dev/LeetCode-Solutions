# Problem Statement: [https://leetcode.com/problems/plus-one/description/](https://leetcode.com/problems/plus-one/description/)
# My Solution: 
```
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int l = digits.size(), c = 0;
        while(l-1 >= 0 && digits[l-1] == 9)
        {
            l--;
            c++;
        }
        vector<int> ans;
        for(int i = 0;i < l-1;i++)
            ans.push_back(digits[i]);
        if(l-1 >= 0)
        { 
            int t = digits[l-1];
            ans.push_back(t+1);
        }
        else if(digits[0] == 9)
            ans.push_back(1);
        for(int i = 1;i <= c;i++)
            ans.push_back(0);
        return ans;
    }
};
```
