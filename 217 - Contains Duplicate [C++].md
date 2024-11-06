# Problem Statement: [https://leetcode.com/problems/contains-duplicate/description/](https://leetcode.com/problems/contains-duplicate/description/)
# My Solution: 
```c
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        map<int, int> f;
        
        for(auto i : nums)
        {
            f[i]++;
            if(f[i] > 1)
                return true;
        }
        return false;
    }
};
```
