# Problem Statement: [https://leetcode.com/problems/missing-number/description/](https://leetcode.com/problems/missing-number/description/)
# My Solution: 
```c
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int sum = n*(n+1)/2, s = 0;

        for(auto i : nums)
            s += i;
        
        return sum-s;
    }
};
```
