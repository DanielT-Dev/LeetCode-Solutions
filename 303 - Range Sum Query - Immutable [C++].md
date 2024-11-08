# Problem Statement: [https://leetcode.com/problems/range-sum-query-immutable/description/](https://leetcode.com/problems/range-sum-query-immutable/description/)
# My Solution: 
```c
class NumArray {
public:

    vector<int> partials;

    NumArray(vector<int>& nums) : partials(nums.size() + 1) {
        partial_sum(nums.begin(), nums.end(), partials.begin() + 1);
    }
    
    int sumRange(int left, int right) {
        return partials[right + 1] - partials[left];
    }

};

/**
 * Your NumArray object will be instantiated and called as such:
 * NumArray* obj = new NumArray(nums);
 * int param_1 = obj->sumRange(left,right);
 */
```
