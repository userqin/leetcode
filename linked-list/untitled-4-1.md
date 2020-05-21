# 82. Remove Duplicates from Sorted List II \(M\)

### [Problem link](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/)

similar to [83 Remove Duplicates from Sorted List \(E\)](https://leetcode.com/problems/remove-duplicates-from-sorted-list/)

### Problem statement

Given a sorted linked list, delete all nodes that have duplicate numbers, leaving only _distinct_ numbers from the original list.

Return the linked list sorted as well.

**Example 1:**

```text
Input: 1->2->3->3->4->4->5
Output: 1->2->5
```

**Example 2:**

```text
Input: 1->1->1->2->3
Output: 2->3
```

### Analysis

### Solution

```python
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution(object):
    def deleteDuplicates(self, head):
        """
        :type head: ListNode
        :rtype: ListNode
        """
        if head == None or head.next == None:
            return head
            
        left = dummy = ListNode(0)
        left.next = curr = head
        while left and left.next:
            if curr.val == curr.next.val:
                left.next = curr.next.next
                curr = curr.next.next
            else:
                left.next = curr
                curr = curr.next
            left = curr
        return dummy.next
```

### References

