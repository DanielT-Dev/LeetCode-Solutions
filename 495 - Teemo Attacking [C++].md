# Problem Statement: [https://leetcode.com/problems/teemo-attacking/description/](https://leetcode.com/problems/teemo-attacking/description/)
# My Solution: 
```c
class Solution {
public:
    int findPoisonedDuration(vector<int>& timeSeries, int duration) {
        int sum = 0;
        int time = 0;
        int n = timeSeries.size();
        for(int i = 0;i < n-1;i++)
        {
            time = timeSeries[i]+duration;
            sum += min(time, timeSeries[i+1])-timeSeries[i];
        }
        sum += duration;
        return sum;
    }
};
```
