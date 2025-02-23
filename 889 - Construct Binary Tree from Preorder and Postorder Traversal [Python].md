# Problem Statement: [Link to Leetcode](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/description/?envType=daily-question&envId=2025-02-23)
# My Solution: 
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def constructFromPrePost(self, preorder: List[int], postorder: List[int]) -> Optional[TreeNode]:

        # preorder = root, left, right
        # postorder = left, right, root
        
        def build(pre, post):

            if not pre:
                return None
            
            # Last element in postorder is the root of the tree
            node = TreeNode(post.pop())

            if len(pre) == 1:
                return node

            # Second last element in postorder is the root of the right subtree

            right_root_index = pre.index(post[-1])

            node.right = build(pre[right_root_index : ], post)
            node.left = build(pre[1 : right_root_index], post)

            return node

        return build(preorder, postorder)
```
