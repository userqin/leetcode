# Reverse a list:  three methods

Given`a = [1, 2, 3, 4, 5]` , we need to reverse it to be`[5, 4, 3, 2, 1]`

**Method 1** ：`list(reversed(a))`  

* `reversed(a)`  returns a iterator, so we need to add list\(\) to it. 

**Method 2:**  `a[start : stop : step]` \# start through, not pass stop, by step.

* `a[::-1]`means starting from the end, counting down to the beginning, stepping backwards one step at a time.
* `a[2:10:2]`means starting from the index -3, counting down to index-10, stepping forwards two steps at a time.
* `a[10:2:-2]`means starting from index-10, counting down to index-2, stepping backwards two steps at a time.
* `a[::2]`means starting from the beginning, counting down to the end, stepping forwards two steps at a time.
* `a[::-2]`means starting from the end, counting down to the beginning, stepping backwards two steps at a time.

**Method 3: use pointers**



