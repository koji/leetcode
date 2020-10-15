## 101. Symmetric Tree

```
Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

For example, this binary tree [1,2,2,3,4,4,3] is symmetric:

    1
   / \
  2   2
 / \ / \
3  4 4  3
 

But the following [1,2,2,null,3,null,3] is not:

    1
   / \
  2   2
   \   \
   3    3
 

Follow up: Solve it both recursively and iteratively.
```

```python
def isSymmetric(self, root: TreeNode) -> bool:
        if not root: return True
        return self.isMirror(root.left, root.right)
        
    def isMirror(self, left, right):
        if not left and not right: return True
        if not left or not right: return False
        if left.val == right.val:
            return self.isMirror(left.left, right.right) and self.isMirror(left.right, right.left)
        else:
            return False

```

```
Runtime: 32 ms, faster than 81.08% of Python3 online submissions for Symmetric Tree.
Memory Usage: 14.1 MB, less than 100.00% of Python3 online submissions for Symmetric Tree.
```
