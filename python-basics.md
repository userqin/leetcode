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

**list.pop\(\)** function returns the element that was removed from a list or an array.

```python
x = [1,2,3,4]
x.pop()
#After this operation, 4 is no longer in x
```

### Remove values by index from a array / list

**list.pop\(index\_of\_the\_element\_to\_be\_removed\)** removes the element according to the index.

```python
x = [1,2,3,4]
x.pop(0)
#After this operation, 1 is no longer in x
```

### list.remove\(\) function 

**list.remove\(\)** is an inbuilt function in Python. It removes a given object from a list or array. It does not return any value.

**list.remove\(element\_to\_be\_removed\)** removes the **element\_to\_be\_removed** from the lowest index.

```python
x = [0, 1, 0,1,0]
x.remove(0)
# x now becomes [1,0, 1, 0]
```

### Summary

* **list.append\(elem\)** -- adds a single element to the end of the list. It modifies the original.
* **list.pop\(index\)** -- removes and returns the element at the given index. Returns the rightmost element if index is omitted \( opposite of **append\(\)**\).
* **list.insert\(index, elem\)** -- inserts the element at the given index, shifting elements to the right.
* **list.extend\(list2\)** adds the elements in list2 to the end of the list.   Using extend\(\) is equivalently to  `list1 + list2 .`
* **list.index\(elem\)** -- searches for the given element from the beginning and returns its index. Throws a  `ValueError` if the element does not appear .
* **list.remove\(elem\)** -- remove the first instance of the given element \(throws `ValueError` 

   if not present\)

* **list.sort\(\)** -- sorts the list in place \(does not return it\).
* **list.reverse\(\)** -- reverses the list in place \(does not return it\).
* **sorted\(list\)** function takes a list and returns a new list. The original is not changed.

### String related

###  Split a string

```python
string = "dog cat cat dog"
words = string.split(' ')
 # the words now is: ['dog', 'cat', 'cat', 'dog']
```

### Convert a list to a string

```text

```

