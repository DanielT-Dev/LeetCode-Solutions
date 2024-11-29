# Problem Statement: [https://leetcode.com/problems/set-mismatch/description/](https://leetcode.com/problems/set-mismatch/description/)
# My Solution: 
```cpp
class Solution {
public:
    vector<int> findErrorNums(vector<int>& nums) {
        vector<int> ans;
        int n = nums.size();
        map<int, int> m;

        for(int i = 0;i < n;i++)
            m[nums[i]] = 0;
        for(int i = 0;i < n;i++)
            m[nums[i]]++;
        for(int i = 1;i <= n;i++)
            if(m[i] == 2)
                ans.push_back(i);
        for(int i = 1;i <= n;i++)
            if(m[i] == 0)
                ans.push_back(i);
        return ans;
    }
};
```
