# Problem Statement: [https://leetcode.com/problems/baseball-game/description/](https://leetcode.com/problems/baseball-game/description/)
# My Solution: 
```cpp
class Solution {
public:
    int calPoints(vector<string>& operations) {
        int sum = 0;
        stack<int> st;
        for(auto i : operations)
        {
            if(i == "+")
            {
                int previous1 = st.top();
                st.pop();
                int previous2 = st.top();
                int current = previous1+previous2;
                st.push(previous1);
                st.push(current);
            }
            else if(i == "C")
                st.pop();
            else if(i == "D")
            {
                int previous1 = st.top();
                st.push(2*previous1);
            }
            else 
                st.push(stoi(i));
        }
        while(!st.empty())
        {
            sum += st.top();
            st.pop();
        }
        return sum;
    }
};
```
