# Problem Statement: [https://leetcode.com/problems/contains-duplicate-ii/description/](https://leetcode.com/problems/contains-duplicate-ii/description/)
# My Solution: 
```c
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
        map<int, int> p;
        int n = nums.size();

        for(auto i : nums)
            p[i] = -1;

        for(int i = 0;i < n;i++)
        {
            if(p[nums[i]] == -1)
                p[nums[i]] = i;
            else 
            {
                if(i-p[nums[i]] <= k)
                    return true;
                p[nums[i]] = i;
            }
        }

        return false;
    }
};
```
