# Problem Statement: [https://leetcode.com/problems/summary-ranges/description/](https://leetcode.com/problems/summary-ranges/description/)
# My Solution: 
```c
class Solution {
public:
    vector<string> summaryRanges(vector<int>& nums) {
        vector<string> v;
        int n = nums.size();
        
        int i = 0;
        while(i < n)
        {
            long long int l = i;
            while(i < n-1 && nums[i]+1 == nums[i+1])
                i++;
            long long int r = i;

            string t;
            if(r-l+1 > 1)
            {
                t = "";
                t += to_string(nums[l]);
                t += "->";
                t += to_string(nums[r]);
            }
            else 
            {
                t = "";
                t += to_string(nums[r]);
            }
            v.push_back(t);

            i++;
        }
        
        return v;
    }
};
```
