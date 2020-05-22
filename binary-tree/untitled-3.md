# 199. Binary Tree Right Side View \(M\)

### [Problem link](untitled-3.md)

### Problem statement

Given a binary tree, imagine yourself standing on the _right_ side of it, return the values of the nodes you can see ordered from top to bottom.

**Example:**

```text
Input: [1,2,3,null,5,null,4]
Output: [1, 3, 4]
Explanation:

   1            <---
 /   \
2     3         <---
 \     \
  5     4       <---
```

### Analysis

### Solution

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def rightSideView(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        """
        if not root:
            return None
        
        q = [root]
        ans = []
        
        while q:
            tmp = []
            for i in range(len()):
                node = q.pop(0)
                tmp.append(node.val)
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
            ans.append(tmp[-1])
        return ans
```

### References

