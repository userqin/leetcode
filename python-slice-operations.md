---
description: 'Slice can be used on lists and strings, which includes start : stop : end.'
---

# Python slice operations

## How it works:

Example

```python
a = [1,2,3]
b = a
c = a[:]
a[0] = 2
print(a) 
print(b)
print(c)
```

We will see the outputs to be:

* `print(a) --> [2, 2, 3]`
* `print(b) --> [2, 2, 3]`
* `print(c) --> [1 ,2, 3]` 



* `s = ['a',  'b', 'c']`
* `s[0:2] returns ['a', 'b']`
* `s[:]`

## Recommendations:

### [Python Slice Examples: Start, Stop and Step](https://www.dotnetperls.com/slice-python)

### [python基础（5）：深入理解 python 中的赋值、引用、拷贝、作用域 ](https://my.oschina.net/leejun2005/blog/145911)

### 

