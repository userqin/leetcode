# 917. Reverse Only Letters \(E\)

### [Problem link](https://leetcode.com/problems/reverse-only-letters/)

### Problem statement

Given a string `S`, return the "reversed" string where all characters that are not a letter stay in the same place, and all letters reverse their positions.

**Example 1:**

```text
Input: "ab-cd"
Output: "dc-ba"
```

**Example 2:**

```text
Input: "a-bC-dEf-ghIj"
Output: "j-Ih-gfE-dCba"
```

**Example 3:**

```text
Input: "Test1ng-Leet=code-Q!"
Output: "Qedo1ct-eeLg=ntse-T!"
```

**Note:**

1. `S.length <= 100`
2. `33 <= S[i].ASCIIcode <= 122` 
3. `S` doesn't contain `\` or `"`

### Analysis

**Method 1**: two pointers

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        """
        
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        """
        
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        """
        
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        """
        
```
{% endtab %}

{% tab title="Two pointers" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        #2020-06-02
        """
        p = 0
        q = len(S) - 1
        ans = list(S)
        
        while p < q:
            while not S[p].isalpha() and p < q:
                 p += 1
            while not S[q].isalpha() and p < q:
                 q -= 1
            if p < q:
                ans[p], ans[q] = ans[q], ans[p]
            p += 1
            q -= 1
        return ''.join(ans)
        
```
{% endtab %}
{% endtabs %}

### References

