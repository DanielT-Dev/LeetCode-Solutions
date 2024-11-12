# Problem Statement: [https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/)
# My Solution: 
```c
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        vector<int> ans;
        map<int, int> m;
    
        for(auto i : nums)
            m[i] = 0;
        for(auto i : nums)
            m[i]++;
        for(int i = 1;i <= nums.size();i++)
            if(m[i] == 0)
                ans.push_back(i);
        
        return ans;
    }
};
```
