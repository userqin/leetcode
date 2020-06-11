# 204. Count Primes

### [Problem link](https://leetcode.com/problems/count-primes/)

### Problem statement

Count the number of prime numbers less than a non-negative number, **n**.

**Example:**

```text
Input: 10
Output: 4
Explanation: There are 4 prime numbers less than 10, they are 2, 3, 5, 7.
```

### Analysis:

**Method 1: brute force**

* Find all composite numbers in the range of `n` and mark them. 
* The unmarked are prime numbers, and number of unmarked numbers is answer to the original problem

### Solution

{% tabs %}
{% tab title="Brute force" %}
```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
        
        def isPrime(n):
            if n <= 1:
                return False
            for i in range(2, n):
                if n % i == 0:
                    return False
            return True
            
        count = 0
        for i in range(n):
        
            
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def countPrimes(self, n):
        """
        :type n: int
        :rtype: int
        """
        
```
{% endtab %}
{% endtabs %}

### References

