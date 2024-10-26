# Problem statement: [https://leetcode.com/problems/two-sum/description/](https://leetcode.com/problems/two-sum/description/)
# My Solution:
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        map<int, int> mm;
        vector<int> t;
        for(int i = 0;i < nums.size();i++)
            mm[nums[i]] = i;
        for(int i = 0;i < nums.size();i++)
            if(mm[target-nums[i]] && i != mm[target-nums[i]])
            {
                t.push_back(i);
                t.push_back(mm[target-nums[i]]);
                return t;
            }
        return t;
    }
};
```
