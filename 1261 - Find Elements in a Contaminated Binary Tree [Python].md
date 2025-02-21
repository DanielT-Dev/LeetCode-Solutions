# Statement: [Link to Leetcode](https://leetcode.com/problems/find-elements-in-a-contaminated-binary-tree/description/?envType=daily-question&envId=2025-02-21)
# Solution:
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class FindElements:

    def __init__(self, root: Optional[TreeNode]):
        
        self.set = set()

        root.val = 0

        q = []
        q.append(root)

        while q:

            node = q.pop()
            self.set.add(node.val)

            if node.left:
                node.left.val = 2 * node.val + 1
                q.append(node.left)

            if node.right:
                node.right.val = 2 * node.val + 2
                q.append(node.right)

    def find(self, target: int) -> bool:
        # Time Complexity: O(1)
        return target in self.set


# Your FindElements object will be instantiated and called as such:
# obj = FindElements(root)
# param_1 = obj.find(target)
```
