# Problem Statement: [https://leetcode.com/problems/longest-harmonious-subsequence/description/](https://leetcode.com/problems/longest-harmonious-subsequence/description/)
# My Solution: 
```c
class Solution {
public:
    int findLHS(vector<int>& nums) {
        map<int, int> m;
        for(auto i : nums)
            m[i] = 0;
        for(auto i : nums)
            m[i]++;
        vector<pair<int, int>> v;
        for(auto i : m)
            v.push_back(i);
        int n = v.size();
        int maximum = 0;
        for(int i = 1;i < n;i++)
            if(v[i].first == v[i-1].first+1)
                maximum = max(maximum, v[i].second+v[i-1].second);
        return maximum;
    }
};
```
