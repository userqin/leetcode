# Tree summary

* [94. Binary Tree Inorder Traversal](https://leetcode.com/problems/binary-tree-inorder-traversal/)
* **95** Unique Binary Search Trees II
* **96** Unique Binary Search Trees
* **98** Validate Binary Search Tree
* **99** Recover Binary Search Tree
* **100** Same Tree
* **101** Symmetric Tree
* **102** Binary Tree Level Order Traversal
* **103** Binary Tree Zigzag Level Order Traversal
* **104** Maximum Depth of Binary Tree
* **105** Construct Binary Tree from Preorder and Inorder Traversal
* **106** Construct Binary Tree from Inorder and Postorder Traversal
* **107** Binary Tree Level Order Traversal II
* **108** Convert Sorted Array to Binary Search Tree
* **109** Convert Sorted List to Binary Search Tree
* **110** Balanced Binary Tree
* **111** Minimum Depth of Binary Tree
* **112** Path Sum
* **113** Path Sum II
* **114** Flatten Binary Tree to Linked List
* **116** Populating Next Right Pointers in Each Node
* **117** Populating Next Right Pointers in Each Node II
* **124** Binary Tree Maximum Path Sum
* **129** Sum Root to Leaf Numbers
* [144. Binary Tree Preorder Traversal](https://leetcode.com/problems/binary-tree-preorder-traversal/)
* [145. Binary Tree Postorder Traversal](https://leetcode.com/problems/binary-tree-postorder-traversal/)
* **173** Binary Search Tree Iterator
* **199** Binary Tree Right Side View
* **222** Count Complete Tree Nodes
* **226** Invert Binary Tree
* **230** Kth Smallest Element in a BST
* **235** Lowest Common Ancestor of a Binary Search Tree
* **236** Lowest Common Ancestor of a Binary Tree
* **257** Binary Tree Paths
* **297** Serialize and Deserialize Binary Tree
* **449**. Serialize and Deserialize BST

## inorder traversal

{% tabs %}
{% tab title="Recursion" %}
```python
# Definition for a binary tree node.
class TreeNode(object):
     def __init__(self, x):
         self.val = x
         self.left = None
         self.right = None

def inOrderTraverse(node):
    if node is None:
        return None
    print(node)
    self.inOrderTraverse(node.left)
    self.inOrderTraverse(node.right)
```
{% endtab %}

{% tab title="non-recursion" %}
```python
# Definition for a binary tree node.
class TreeNode(object):
     def __init__(self, x):
         self.val = x
         self.left = None
         self.right = None


```
{% endtab %}

{% tab title="" %}
```python

```
{% endtab %}
{% endtabs %}

