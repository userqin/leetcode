---
description: Summary of basics that might be used in leetcode
---

# Python basics

## Array  and List related 

### Add values to the end of a array / list

```python
x = [1,2,3]
x.append(new_element)
```

### Remove values from the end of a array / list

**pop\(\)** function returns the element that was removed from a list or an array.

```python
x = [1,2,3,4]
x.pop()
#After this operation, 4 is no longer in x
```

### Remove values by index from a array / list

**pop\(index\_of\_the\_element\_to\_be\_removed\)** removes the element according to the index.

```python
x = [1,2,3,4]
x.pop(0)
#After this operation, 1 is no longer in x
```

### remove\(\) function 

**remove\(\)** is an inbuilt function in Python. It removes a given object from a list or array. It does not return any value.

**remove\(element\_to\_be\_removed\)** removes the **element\_to\_be\_removed** from the lowest index.

```python
x = [0, 1, 0,1,0]
x.remove(0)
# x now becomes [1,0, 1, 0]
```

### String related

### split a string

```python
string = "dog cat cat dog"
words = string.split(' ')
 # the words now is: ['dog', 'cat', 'cat', 'dog']
```



