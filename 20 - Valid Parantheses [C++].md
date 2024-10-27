# Problem Statement: [https://leetcode.com/problems/valid-parentheses/description/](https://leetcode.com/problems/valid-parentheses/description/)
# My Solution:
```
class Solution {
public:
    bool isValid(string s) {
        stack<char> st;
        for(auto e : s)
        {
            if(st.empty() == false)
            {
                if(st.top() == '(' && e == ')')
                    st.pop();
                else if(st.top() == '[' && e == ']')
                    st.pop();
                else if(st.top() == '{' && e == '}')
                    st.pop();
                else if(e == '(' || e == '[' || e == '{')
                    st.push(e);
                else 
                    return false;
            }
            else 
                st.push(e);
        }
        return st.empty() == true;
    }
};
```
