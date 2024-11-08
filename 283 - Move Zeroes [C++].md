# Problem Statement: [https://leetcode.com/problems/move-zeroes/description/](https://leetcode.com/problems/move-zeroes/description/)
# My Solution: 
```c
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n = nums.size();
        int c = 0;

        for(int i = 0;i < n;i++)
            if(nums[i] == 0)
            {
                for(int j = i+1;j < n;j++)
                    nums[j-1] = nums[j];
                c++;
                n--;
                i--;
            }
        for(int i = n;i < n+c;i++)
            nums[i] = 0;
    }
};
```
