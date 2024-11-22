# Problem Statement: [https://leetcode.com/problems/range-addition-ii/description/](https://leetcode.com/problems/range-addition-ii/description/)
# My Solution: 
```c
class Solution {
public:
    int maxCount(int m, int n, vector<vector<int>>& ops) {
        int minX = m+1, minY = n+1;
        for(auto i : ops)
        {
            int x = i[0];
            int y = i[1];
            if(x < minX)
            {
                minX = x;
            }
            if(y < minY)
            {
                minY = y;
            }
        }
        if(ops.empty())
            return m*n;
        return minX*minY;
    }
};
```
