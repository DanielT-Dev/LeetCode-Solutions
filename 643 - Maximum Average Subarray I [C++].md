# Problem Statement: [https://leetcode.com/problems/maximum-average-subarray-i/description/](https://leetcode.com/problems/maximum-average-subarray-i/description/)
# My Solution: 
```cpp
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        int n = nums.size();
        int sum = 0;

        for(int i = 0;i < k;i++)
            sum += nums[i];
        
        double maxAverage = (double)sum/k;

        for(int i = k;i < n;i++)
        {
            sum -= nums[i-k];
            sum += nums[i];

            if((double)sum/k > maxAverage)
                maxAverage = (double)sum/k;
        }

        return maxAverage;
    }
};
```
