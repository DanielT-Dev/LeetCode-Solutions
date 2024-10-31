# Problem Statement: [https://leetcode.com/problems/binary-tree-inorder-traversal/description/](https://leetcode.com/problems/binary-tree-inorder-traversal/description/)
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

    vector<int> solution;

    void inorder(TreeNode* currentNode)
    {
        if(currentNode)
        {
            if(currentNode->left)
                inorder(currentNode->left);
            solution.push_back(currentNode->val);
            if(currentNode->right)
                inorder(currentNode->right);
        }
    }

    vector<int> inorderTraversal(TreeNode* root) {
        inorder(root);
        return solution;
    }
};
```
