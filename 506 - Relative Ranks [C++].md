# Problem Statement: [https://leetcode.com/problems/relative-ranks/description/](https://leetcode.com/problems/relative-ranks/description/)
# My Solution: 
```c
class Solution {
public:
    vector<string> findRelativeRanks(vector<int>& score) {
        vector<string> ans(score.size());
        int n = score.size();
        vector<pair<int, int>> secondary;
        for(int i = 0;i < n;i++)
            secondary.push_back({score[i], i});
        sort(secondary.rbegin(), secondary.rend());
        for(int i = 0;i < n;i++)
        {
            if(i == 0)
                ans[secondary[i].second] = "Gold Medal";
            else if(i == 1)
                ans[secondary[i].second] = "Silver Medal";
            else if(i == 2)
                ans[secondary[i].second] = "Bronze Medal";
            else
                ans[secondary[i].second] = to_string(i+1);
        }
        return ans;
    }
};
```
