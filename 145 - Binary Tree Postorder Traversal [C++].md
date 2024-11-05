# Problem Statement: [https://leetcode.com/problems/binary-tree-postorder-traversal/description/](https://leetcode.com/problems/binary-tree-postorder-traversal/description/)
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

    void postorder(TreeNode* current)
    {
        if(current)
        {
            postorder(current->left);
            postorder(current->right);
            v.push_back(current->val);
        }
    }

    vector<int> postorderTraversal(TreeNode* root) {
        postorder(root);
        return v;
    }
};
```
