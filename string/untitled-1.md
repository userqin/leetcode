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

**Method 2**: one pointer: use one pointer `p` to locate the letters from the end of the string and swap with the one in the beginning of the string

**Method 3**: Save all the letters first, and then traverse the string again. If a position of the original string is a letter, then replace it with the last element in the letter list, otherwise it will be the original character.

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

{% tab title="extra space" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        :2020-06-02
        """
        letters = []
        for l in S:
            if l.isalpha():
                letters.append(l)
        ans = ''
        for i in range(len(S)):
            if S[i].isalpha():
                ans += letters.pop()
            else:
                ans += S[i]
        return ans
        
```
{% endtab %}

{% tab title="One pointer" %}
```python
class Solution(object):
    def reverseOnlyLetters(self, S):
        """
        :type S: str
        :rtype: str
        #2020-06-02
        """
        p = len(S) - 1
        ans = ''
        for i in range(len(S)):
            if S[i].isalpha():
                while not S[p].isalpha():
                    p -= 1
                ans += S[p]
                p -= 1
            else:
                ans += S[i]
        return ans
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

