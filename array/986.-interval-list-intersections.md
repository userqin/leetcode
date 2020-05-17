# 986. Interval List Intersections

### [Problem link](https://leetcode.com/problems/interval-list-intersections/)

### Problem statement

Given two lists of **closed** intervals, each list of intervals is pairwise disjoint and in sorted order.

Return the intersection of these two interval lists.

_\(Formally, a closed interval `[a, b]` \(with `a <= b`\) denotes the set of real numbers `x` with `a <= x <= b`.  The intersection of two closed intervals is a set of real numbers that is either empty, or can be represented as a closed interval.  For example, the intersection of \[1, 3\] and \[2, 4\] is \[2, 3\].\)_

**Example 1:**

![](https://assets.leetcode.com/uploads/2019/01/30/interval1.png)

```text
Input: A = [[0,2],[5,10],[13,23],[24,25]], B = [[1,5],[8,12],[15,24],[25,26]]
Output: [[1,2],[5,5],[8,10],[15,23],[24,24],[25,25]]
Reminder: The inputs and the desired output are lists of Interval objects, and not arrays or lists.
```

**Note:**

1. `0 <= A.length < 1000`
2. `0 <= B.length < 1000`
3. `0 <= A[i].start, A[i].end, B[i].start, B[i].end < 10^9`

**NOTE:** input types have been changed on April 15, 2019. Please reset to default code definition to get new method signature.

### Analysis

### Solution

```python
class Solution(object):
    def intervalIntersection(self, A, B):
        """
        :type A: List[List[int]]
        :type B: List[List[int]]
        :rtype: List[List[int]]
        """
        A.sort(key = lambda x: x[0])
        B.sort(key = lambda x: x[0])
        
        if not A or not B:
            return None
        ans = []
        p1, p2 = 0, 0
        while p1 < len(A) and p2 < len(B):
            start = max(A[p1][0], B[p2][0])
            end = min(A[p1][1], B[p2][1])
            if start <= end:
                ans.append([start, end])
            if A[p1][1] < B[p2][1] :
                p1 += 1
            else:
                p2 += 1
        return ans
```

### References



