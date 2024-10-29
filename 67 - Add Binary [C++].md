# Problem Statement: [https://leetcode.com/problems/add-binary/description/](https://leetcode.com/problems/add-binary/description/)
# My Solution: 
```
class Solution {
public:
    string addBinary(string a, string b) {
        int ia = a.length()-1;
        int ib = b.length()-1;

        string rever = "";
        int t = 0;
        while(ia >= 0 || ib >= 0 || t != 0)
        {
            int s = 0;
            if(ia >= 0)
            {
                s += a[ia]-'0';
                ia--;
            }
            if(ib >= 0)
            {
                s += b[ib]-'0';
                ib--;
            }

            s += t;
            t = s/2;
            s %= 2;
            
            cout<<s<<' ';
            rever += s+'0';
        }

        string ans = "";
        for(int i = rever.length() - 1;i >= 0;i--)
            ans += rever[i];
        
        return ans;
    }
};
```
