---
description: two pointers
---

# 905. Sort Array By Parity

### [Problem link](https://leetcode.com/problems/sort-array-by-parity/)

### Problem statement

Given an array `A` of non-negative integers, return an array consisting of all the even elements of `A`, followed by all the odd elements of `A`.

You may return any answer array that satisfies this condition.

**Example 1:**

```text
Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
```

**Note:**

1. `1 <= A.length <= 5000`
2. `0 <= A[i] <= 5000`

### Analysis:

**Methond 1**: two pointers

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        """
```
{% endtab %}

{% tab title="two pointers" %}
```python
class Solution(object):
    def sortArrayByParity(self, A):
        """
        :type A: List[int]
        :rtype: List[int]
        #2020-06-03
        """
        left = 0
        right = len(A) - 1
        while left < right:
            while left < right and A[left] % 2 == 0:
                left += 1
            A[left], A[right] = A[right], A[left]
            right -= 1
        return A
```
{% endtab %}
{% endtabs %}

### References

