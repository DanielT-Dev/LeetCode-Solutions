# Problem Statement: [https://leetcode.com/problems/minimum-index-sum-of-two-lists/description/](https://leetcode.com/problems/minimum-index-sum-of-two-lists/description/)
# My Solution: 
```c
class Solution {
public:
    vector<string> findRestaurant(vector<string>& list1, vector<string>& list2) {
        vector<string> ans;
        map<string, int> m1, m2;
        int minimum = 1000000;
        int n1 = list1.size(), n2 = list2.size();
        for(int i = 0;i < n1;i++)
            m1[list1[i]] = i+1;
        for(int i = 0;i < n2;i++)
            m2[list2[i]] = i+1;
        for(int i = 0;i < n1;i++)
        {
            string commonString = list1[i];
            if(!m1[commonString] || !m2[commonString])
                continue;
            if(m1[commonString] + m2[commonString] < minimum)
            {
                ans.clear();
                minimum = m1[commonString]+m2[commonString];
                ans.push_back(commonString);
            }
            else if(m1[commonString]+m2[commonString] == minimum)
                ans.push_back(commonString);
        }
        return ans;
    }
};
```
