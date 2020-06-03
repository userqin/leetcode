# 227. Basic Calculator II \(M\)

### [Problem link](https://leetcode.com/problems/basic-calculator-ii/)

### Problem statement

Implement a basic calculator to evaluate a simple expression string.

The expression string contains only **non-negative** integers, `+`, `-`, `*`, `/` operators and empty spaces . The integer division should truncate toward zero.

**Example 1:**

```text
Input: "3+2*2"
Output: 7
```

**Example 2:**

```text
Input: " 3/2 "
Output: 1
```

**Example 3:**

```text
Input: " 3+5 / 2 "
Output: 5
```

**Note:**

* You may assume that the given expression is always valid.
* **Do not** use the `eval` built-in library function.

### Analysis

Since the expression string does not contain parentheses, the problem can be simplified to deal with the priority of \(multiplication & division\) operations and \(addition & subtraction operations\).

* ~~use an auxiliary variable `d` to record current numbers to be involved, an auxiliary variable `func` to record last operator, and `total` to record the resulting number.~~
* ~~If current operator is multiplication and division, then do multiplication or division for current number d with the next number, and assign the result to d.~~
* ~~If current operator is addition and subtraction, then perform `func` \(addition and subtraction\) operactions on total and d, and assign values to total, and update `func`~~ [~~`http://bookshadow.com/weblog/2015/06/23/leetcode-basic-calculator-ii/`~~](http://bookshadow.com/weblog/2015/06/23/leetcode-basic-calculator-ii/)
* To realize the priorities of operations, use
  * `stack` to save operands.
  * `num` to save the previous operand.
  * `prev_operator` is to save the previous operator. When we meet a new operator, compare it to `prev_operator` to determine which operations to be carried out \(`* / + -`\)
* when `prev_operator == '*'` dition & , 

### Solution

{% tabs %}
{% tab title="Python" %}
```python
class Solution(object):
    def calculate(self, s):
        """
        :type s: str
        :rtype: int
        """
        #2020-06-02
        stack = []
        prev_operator = '+'
        num = 0
        for i in range(len(s)):
            if s[i].isdigit():
                num = 10 * num + int(s[i])
            if i == len(s) - 1 or s[i] in '+-*/':
                if prev_operator == '+':
                    stack.append(num)
                elif prev_operator == '-':
                    stack.append(-num)
                elif prev_operator == '*':
                    stack.append(stack.pop() * num)
                elif prev_operator == '/':
                    top = stack.pop() 
                    if top < 0:
                        stack.append(-1*(-1*top//num))
                    else:
                        stack.append(top//num)
                prev_operator = s[i]
                num = 0
        return sum(stack)
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def calculate(self, s):
        """
        :type s: str
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def calculate(self, s):
        """
        :type s: str
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def calculate(self, s):
        """
        :type s: str
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def calculate(self, s):
        """
        :type s: str
        :rtype: int
        """
```
{% endtab %}
{% endtabs %}

### References

[https://blog.csdn.net/kuaisuzhuceh/article/details/50611148](https://blog.csdn.net/kuaisuzhuceh/article/details/50611148)

[https://blog.csdn.net/fuxuemingzhu/article/details/80826333](https://blog.csdn.net/fuxuemingzhu/article/details/80826333)



