---
description: 'for i in range(1, len(chars) + 1):'
---

# 443. String Compression \(E\)

### [Problem link](https://leetcode.com/problems/string-compression/)

### Problem statement

Given an array of characters, compress it [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm).

The length after compression must always be smaller than or equal to the original array.

Every element of the array should be a **character** \(not int\) of length 1.

After you are done **modifying the input array** [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm), return the new length of the array. 

**Follow up:**  
Could you solve it using only O\(1\) extra space? 

**Example 1:**

```text
Input:
["a","a","b","b","c","c","c"]

Output:
Return 6, and the first 6 characters of the input array should be: ["a","2","b","2","c","3"]

Explanation:
"aa" is replaced by "a2". "bb" is replaced by "b2". "ccc" is replaced by "c3".
```

**Example 2:**

```text
Input:
["a"]

Output:
Return 1, and the first 1 characters of the input array should be: ["a"]

Explanation:
Nothing is replaced.
```

**Example 3:**

```text
Input:
["a","b","b","b","b","b","b","b","b","b","b","b","b"]

Output:
Return 4, and the first 4 characters of the input array should be: ["a","b","1","2"].

Explanation:
Since the character "a" does not repeat, it is not compressed. "bbbbbbbbbbbb" is replaced by "b12".
Notice each digit has it's own entry in the array.
```

**Note:**

1. All characters have an ASCII value in `[35, 126]`.
2. `1 <= len(chars) <= 1000`.

### Analysis

**Method 1**: two pointers \(`left` and `i`\)

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def compress(self, chars):
        """
        :type chars: List[str]
        :rtype: int
        """
        left = 0
        
        count = 1
        for i in range(1, len(chars)):
            if i < len(chars) and chars[i] == chars[i - 1]:
                count += 1
            else:
                chars[left] = chars[i-1]
                left += 1
                if count > 1:
                    for n in str(count):
                        chars[left] = n
                        left += 1
                count = 1
        return left
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def compress(self, chars):
        """
        :type chars: List[str]
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def compress(self, chars):
        """
        :type chars: List[str]
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def compress(self, chars):
        """
        :type chars: List[str]
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def compress(self, chars):
        """
        :type chars: List[str]
        :rtype: int
        """
```
{% endtab %}
{% endtabs %}

### References

