# Problem Statement: [https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)
# My Solution: 
```
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int n = nums.size();
        for(int i = 0;i < n-1;i++)
            if(nums[i] == nums[i+1])
            {
                for(int j = i;j < n-1;j++)
                    nums[j] = nums[j+1];
                i--;
                n--;
            }
        return n;
    }
};
```
