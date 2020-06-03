# 859. Buddy Strings \(E\)

### [Problem link](https://leetcode.com/problems/buddy-strings/)

### Problem statement

Given two strings `A` and `B` of lowercase letters, return `true` if and only if we can swap two letters in `A` so that the result equals `B`.

**Example 1:**

```text
Input: A = "ab", B = "ba"
Output: true
```

**Example 2:**

```text
Input: A = "ab", B = "ab"
Output: false
```

**Example 3:**

```text
Input: A = "aa", B = "aa"
Output: true
```

**Example 4:**

```text
Input: A = "aaaaaaabc", B = "aaaaaaacb"
Output: true
```

**Example 5:**

```text
Input: A = "", B = "aa"
Output: false
```

**Note:**

1. `0 <= A.length <= 20000`
2. `0 <= B.length <= 20000`
3. `A` and `B` consist only of lowercase letters.

### Analysis:

* If the lengths of two strings are not equal, then must be `False`
* If unique letters of two strings are not the same, then must be `False`
* If two strings are identical, if there are at least two letters are identical, then `True`
* If the lengths of two stings are the same and only two letters are not the same, record these two letters' position. If switching the positions of these two letters
* if two strings have more than 2 different characters, we can never get the same string by one swap, thus return `False`
* if only two letters are different while traversing two strings,  let's swap and check if swapping can get the same result.

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def buddyStrings(self, a, b):
        """
        :type A: str
        :type B: str
        :rtype: bool
        """
        if len(a) != len(b) or set(a) != set():
            return False
        
        diff = 0
        indices = []
        for i in range(len(a)):
            if b[i] != a[i]:
                diff += 1
                indices.append(i)
        d = {}
        if diff == 0: 
        #when a is identical to b, we need to find at least two letters in the string so tha
        # we can swap a to get b
            for s in a:
                if s in d:
                    return True
                else:
                    d[s] = True
        if diff != 2:
            return False
        if diff == 2 and a[indices[0]] == b[indices[1]] and a[indices[1]] == b[indices[0]]:
            return True
        return False
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def buddyStrings(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: bool
        """
        
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def buddyStrings(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: bool
        """
        
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def buddyStrings(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: bool
        """
        
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def buddyStrings(self, A, B):
        """
        :type A: str
        :type B: str
        :rtype: bool
        """
        
```
{% endtab %}
{% endtabs %}

### References

