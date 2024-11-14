# Problem Statement: [https://leetcode.com/problems/max-consecutive-ones/description/](https://leetcode.com/problems/max-consecutive-ones/description/)
# My Solution: 
```c
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int n = nums.size();
        int i = 0;
        int past, ans = 0;

        while(i < n && nums[i] == 0)
            i++;
        
        past = i;
        while(i < n)
        {
            if(nums[i] == 1)
                ans = max(ans, i-past+1);
            else if(nums[i] == 0)
            {
                while(i < n && nums[i] == 0)
                    i++;
                past = i;
            }
            i++;
        }

        return ans;
    }
};
```
