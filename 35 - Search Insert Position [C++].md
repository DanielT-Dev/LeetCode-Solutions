# Problem Statement: [https://leetcode.com/problems/search-insert-position/description/](https://leetcode.com/problems/search-insert-position/description/)
# My Solution:
```
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int c = 0;
        for(auto i : nums)
            if(i < target)
                c++;
        return c;
    }
};
```
