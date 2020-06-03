# 657. Robot Return to Origin \(E\)

### [Problem link](https://leetcode.com/problems/robot-return-to-origin/)

### Problem statement

There is a robot starting at position \(0, 0\), the origin, on a 2D plane. Given a sequence of its moves, judge if this robot **ends up at \(0, 0\)** after it completes its moves.

The move sequence is represented by a string, and the character moves\[i\] represents its ith move. Valid moves are R \(right\), L \(left\), U \(up\), and D \(down\). If the robot returns to the origin after it finishes all of its moves, return true. Otherwise, return false.

**Note**: The way that the robot is "facing" is irrelevant. "R" will always make the robot move to the right once, "L" will always make it move left, etc. Also, assume that the magnitude of the robot's movement is the same for each move.

**Example 1:**

```text
Input: "UD"
Output: true 
Explanation: The robot moves up once, and then down once. All moves have the same magnitude, so it ended up at the origin where it started. Therefore, we return true.
```

**Example 2:**

```text
Input: "LL"
Output: false
Explanation: The robot moves left twice. It ends up two "moves" to the left of the origin. We return false because it is not at the origin at the end of its moves.
```

### Analysis

### Solution

{% tabs %}
{% tab title="hashmap" %}
```python
class Solution(object):
    def judgeCircle(self, moves):
        """
        :type moves: str
        :rtype: bool
        """
        s = 'LRUD'
        d = dict.fromkeys(s,0)
        
        for s in moves:
            d[s] += 1
        if d['L'] == d['R'] and d['U'] == d['D']:
            return True
        return False
```
{% endtab %}

{% tab title="simulation" %}
```python
class Solution(object):
    def judgeCircle(self, moves):
        """
        :type moves: str
        :rtype: bool
        """
        ans = [0,0]
        for i in range(len(moves)):
            if moves[i] == 'L':
                ans[0] -= 1
            if moves[i] == 'R':
                ans[0] += 1
            if moves[i] == 'U':
                ans[1] += 1
            if moves[i] == 'D':
                ans[1] -= 1
        if ans == [0,0]:
            return True
        return False
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def judgeCircle(self, moves):
        """
        :type moves: str
        :rtype: bool
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def judgeCircle(self, moves):
        """
        :type moves: str
        :rtype: bool
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def judgeCircle(self, moves):
        """
        :type moves: str
        :rtype: bool
        """
```
{% endtab %}
{% endtabs %}

### References

