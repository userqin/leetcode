# Problems in python

### How to find the key of the maximum value in a dictionary ?

`d = d.fromkeys('abcdefg',0)`

`max() function always return one, be careful for a = [3,3,2,1] the max(a) corresponds to two indices.`

### `How to remove duplicates in a list ?`

```python
s1 = [1, 2, 1, 4, 4, 3]
s2 = [[1,1], [2,2], [1,4],[1,1], [2,2], [3, 5]] 
s3 = [(1, 1), (2, 4), (4, 3), (5, 6), (1, 1), (2, 2)]
s4 = ((1, 1), (2, 4), (4, 3), (5, 6), (1, 1), (2, 2))

s1_set = set(s1)
s2_set = set(map(tuple,s2))
s3_set = set(s3)
s4_set = set(s4)

# s2 cannot be set() directly, it will result in a 
#TypeError: unhashable type: 'list'
```



