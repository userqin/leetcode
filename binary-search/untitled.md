# 1351. Count Negative Numbers in a Sorted Matrix \(E\)

### [Problem link](https://leetcode.com/problems/count-negative-numbers-in-a-sorted-matrix/)

### Problem statement



Given a `m * n` matrix `grid` which is sorted in non-increasing order both row-wise and column-wise. 

Return the number of **negative** numbers in `grid`.

**Example 1:**

```text
Input: grid = [[4,3,2,-1],[3,2,1,-1],[1,1,-1,-2],[-1,-1,-2,-3]]
Output: 8
Explanation: There are 8 negatives number in the matrix.
```

**Example 2:**

```text
Input: grid = [[3,2],[1,0]]
Output: 0
```

**Example 3:**

```text
Input: grid = [[1,-1],[-1,-1]]
Output: 3
```

**Example 4:**

```text
Input: grid = [[-1]]
Output: 1
```

**Constraints:**

* `m == grid.length`
* `n == grid[i].length`
* `1 <= m, n <= 100`
* `-100 <= grid[i][j] <= 100`

### Analysis

### Solution

```python
class Solution(object):
    def countNegatives(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        # for each row from left to right, descending order
        # for each col from top to bottom, descending order
 
```

### References

