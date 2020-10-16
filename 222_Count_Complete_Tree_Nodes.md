## 222. Count Complete Tree Nodes

```
Given a complete binary tree, count the number of nodes.

Note:

Definition of a complete binary tree from Wikipedia:
In a complete binary tree every level, except possibly the last, is completely filled, and all nodes in the last level are as far left as possible. It can have between 1 and 2h nodes inclusive at the last level h.

Example:

Input: 
    1
   / \
  2   3
 / \  /
4  5 6

Output: 6

```


```python
class Solution:
    def countNodes(self, root: TreeNode) -> int:
        if not root: return 0
        # check depth
        ld = self.check_depth(root, True)
        rd = self.check_depth(root, False)
        # print(ld)
        # print(rd)
        if ld == rd:
            return int(math.pow(2, ld)-1)
        return int(1 + self.countNodes(root.left) + self.countNodes(root.right))
        
    def check_depth(self, root, lr):
        if not root: return 0
        if lr:
            d = self.check_depth(root.left, lr)
        else:
            d = self.check_depth(root.right, lr)

        return d + 1
```

```
Runtime: 64 ms, faster than 98.98% of Python3 online submissions for Count Complete Tree Nodes.
Memory Usage: 21.3 MB, less than 100.00% of Python3 online submissions for Count Complete Tree Nodes.

```
