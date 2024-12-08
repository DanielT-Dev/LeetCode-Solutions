# Problem Statement: [https://leetcode.com/problems/find-pivot-index/description/](https://leetcode.com/problems/find-pivot-index/description/)
# My Solution: 
```cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int total_sum = 0;
        for(auto i : nums)
            total_sum += i;
        int sum = 0, ind = 0;
        for(auto i : nums)
        {
            if(total_sum-sum-i == sum)
                return ind;
            sum += i;
            ind++;
        }
        return -1;
    }
};
```
