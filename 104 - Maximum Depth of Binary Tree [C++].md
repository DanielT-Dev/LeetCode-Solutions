# Problem Statement: [https://leetcode.com/problems/maximum-depth-of-binary-tree/description/](https://leetcode.com/problems/maximum-depth-of-binary-tree/description/)
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



    int maxDepth(TreeNode* root) {
        if(root)
        {
            int p = 1;
            if(root->left)
                p = max(p, 1 + maxDepth(root->left));
            if(root->right)
                p = max(p, 1 + maxDepth(root->right));
            return p;
        }
        return 0;
    }
};
```
