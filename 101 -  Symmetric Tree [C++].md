# Problem Statement: [https://leetcode.com/problems/symmetric-tree/description/](https://leetcode.com/problems/symmetric-tree/description/)
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

    bool isPalindrome(vector<int> x)
    {
        int l = x.size();
        for(int i = 0;i <= l/2;i++)
            if(x[i] != x[l-i-1])
                return false;
        return true;
    }

    bool isSymmetric(TreeNode* root) {
        if(!root)
            return true;
        
        queue<TreeNode*> nodes;

        if(root->left)
            nodes.push(root->left);
        else 
            nodes.push(NULL);
        if(root->right)
            nodes.push(root->right);
        else 
            nodes.push(NULL);

        while(nodes.empty() == false)
        {
            int l = nodes.size();
            vector<int> x;
            for(int i = 1;i <= l;i++)
            {
                TreeNode* current = nodes.front();
                if(current)
                    x.push_back(current->val);
                else 
                    x.push_back(-1234);
                if(current)
                {
                    if(current->left)
                        nodes.push(current->left);
                    else
                        nodes.push(NULL);
                    if(current->right)
                        nodes.push(current->right);
                    else
                        nodes.push(NULL);
                }
                nodes.pop();
            }
            if(!isPalindrome(x))
                return false;
        }
        return true;
    }
};
```
