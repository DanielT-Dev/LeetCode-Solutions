# Problem Statement: [https://leetcode.com/problems/path-sum/description/](https://leetcode.com/problems/path-sum/description/)
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

    bool isLeaf(TreeNode* current)
    {
        if(!current)
            return false;
        return  !current->left && !current->right;
    }

    bool hasPathSum(TreeNode* root, int targetSum) {
        if(!root && targetSum == 0)
            return false;
        if(!root)
            return false;
        return (isLeaf(root) && targetSum-root->val == 0) || 
        hasPathSum(root->left, targetSum-root->val) || hasPathSum(root->right, targetSum-root->val);
    }
};
```
