# 541. Reverse String II \(E\)

### [Problem link](https://leetcode.com/problems/reverse-string-ii/)

similar problem: [561. Array Partition I \(E\)](https://leetcode.com/problems/array-partition-i/)

### Problem statement

Given a string and an integer k, you need to reverse the first k characters for every 2k characters counting from the start of the string. If there are less than k characters left, reverse all of them. If there are less than 2k but greater than or equal to k characters, then reverse the first k characters and left the other as original.

**Example:**

```text
Input: s = "abcdefg", k = 2
Output: "bacdfeg"
```

**Restrictions:**

1. The string consists of lower English letters only.
2. Length of the given string and k will in the range \[1, 10000\]

### Analysis

### Solution

{% tabs %}
{% tab title="simulation" %}
```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
        count = 0
        ans = ''
        for i in range(0, len(s), k):
            if count % 2 == 0:
                if i + k > len(s):
                    tmp = s[i:][::-1]
                else:
                    tmp = s[i:i+k][::-1]
            else:
                if i + k > len(s):
                    tmp = s[i:][::-1]
                else:
                    tmp = s[i:i+k]
            ans += tmp
            count += 1
        return ans
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseStr(self, s, k):
        """
        :type s: str
        :type k: int
        :rtype: str
        """
```
{% endtab %}
{% endtabs %}

### References

