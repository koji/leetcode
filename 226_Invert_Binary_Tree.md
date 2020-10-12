226. Invert Binary Tree

Invert a binary tree.

Example:

Input:

     4
   /   \
  2     7
 / \   / \
1   3 6   9
Output:

     4
   /   \
  7     2
 / \   / \
9   6 3   1

```python
    def invertTree(self, root: TreeNode) -> TreeNode:
        if root == None:
            return
        else:
            root.left, root.right = root.right, root.left
            self.invertTree(root.left)
            self.invertTree(root.right)
        return root
```
