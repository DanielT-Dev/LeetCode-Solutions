# Problem Statement: [https://leetcode.com/problems/binary-search/description/](https://leetcode.com/problems/binary-search/description/)
# My Solution: 
```cpp
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int left = 0, right = nums.size()-1;
        while(left <= right)
        {
            int middle = (left+right)/2;
            if(nums[middle] == target)
                return middle;
            else if(nums[middle] < target)
                left = middle+1;
            else if(nums[middle] > target)
                right = middle-1;
        }
        return -1;
    }
};
```
