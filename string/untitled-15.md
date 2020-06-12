# 557. Reverse Words in a String III \(E\)

### [Problem link](https://leetcode.com/problems/reverse-words-in-a-string-iii/)

### Problem statement

Given a string, you need to reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

**Example 1:**

```text
Input: "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```

**Note:** In the string, each word is separated by single space and there will not be any extra space in the string.

### Analysis

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        l = list(s)[::-1]
        l = ''.join(l)
        tmp = l.split(' ')[::-1]
        return ' '.join(tmp)
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
```
{% endtab %}
{% endtabs %}

### References

