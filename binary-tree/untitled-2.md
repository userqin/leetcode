# 103. Binary Tree Zigzag Level Order Traversal \(M\)

### [Problem link](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal/)

### Problem statement

Given a binary tree, return the zigzag level order traversal of its nodes' values. \(ie, from left to right, then right to left for the next level and alternate between\).

For example:  
Given binary tree `[3,9,20,null,null,15,7]`,  


```text
    3
   / \
  9  20
    /  \
   15   7
```

return its zigzag level order traversal as:  


```text
[
  [3],
  [20,9],
  [15,7]
]
```

### Analysis

### Solution

{% tabs %}
{% tab title="Python" %}
```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def zigzagLevelOrder(self, root):
        """
        :type root: TreeNode
        :rtype: List[List[int]]
        """
        
        if not root:
            return None
        q = [root]
        level = 0
        ans = []
        while q:
            tmp = []
            for i in range(len(q)):
                node = q.pop(0)
                tmp.append(node.val)
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
            if level % 2 == 0:
                ans.append(tmp)
            else:
                ans.append(tmp[::-1])
            level += 1
        return ans
                    
```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}
{% endtabs %}

### References

