# Problem Statement: [https://leetcode.com/problems/longest-continuous-increasing-subsequence/description/](https://leetcode.com/problems/longest-continuous-increasing-subsequence/description/)
# My Solution: 
```cpp
class Solution {
public:
    int findLengthOfLCIS(vector<int>& nums) {
        int n = nums.size();
        int start = 0, maxLength = 1;

        for(int i = 1;i < n;i++)
            if(nums[i-1] < nums[i])
                continue;
            else 
            {
                if(i-1-start+1 > maxLength)
                    maxLength = i-1-start+1;
                start = i;
            }
        if(n-1-start+1 > maxLength)
            maxLength = n-1-start+1;
        return maxLength;
    }
};
```
