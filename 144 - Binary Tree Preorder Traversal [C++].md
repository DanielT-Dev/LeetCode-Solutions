# Problem Statement: [https://leetcode.com/problems/binary-tree-preorder-traversal/description/](https://leetcode.com/problems/binary-tree-preorder-traversal/description/)
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

    vector<int> v;

    void preorder(TreeNode* current)
    {
        if(current)
        {
            v.push_back(current->val);
            preorder(current->left);
            preorder(current->right);
        }
    }

    vector<int> preorderTraversal(TreeNode* root) {
        preorder(root);
        return v;
    }
};
```
