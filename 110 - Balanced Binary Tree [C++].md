# Problem Statement: [https://leetcode.com/problems/balanced-binary-tree/description/](https://leetcode.com/problems/balanced-binary-tree/description/)
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

    int maxDepth(TreeNode* current)
    {
        if(!current)
            return 0;
        return 1+max(maxDepth(current->left), maxDepth(current->right));
    }

    bool isBalanced(TreeNode* root) {
        if(!root)
            return true;
        return abs(maxDepth(root->left) - maxDepth(root->right)) <= 1 &&
           isBalanced(root->left) && isBalanced(root->right);
    }
};
```
