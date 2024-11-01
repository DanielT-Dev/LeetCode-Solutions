# Problem Statement: [https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/)
# My Solution: 
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    TreeNode* build(vector<int> v, int l, int r)
    {
        if(l > r)
            return nullptr;
        int m = (l+r)/2;
        return new TreeNode(v[m], build(v, l, m-1), build(v, m+1, r));
    }

    TreeNode* sortedArrayToBST(vector<int>& nums) {
        return build(nums, 0, nums.size()-1);
    }
};
```
