# 874. Walking Robot Simulation

### [Problem link](https://leetcode.com/problems/walking-robot-simulation/)

### Problem statement

A robot on an infinite grid starts at point \(0, 0\) and faces north.  The robot can receive one of three possible types of commands:

* `-2`: turn left 90 degrees
* `-1`: turn right 90 degrees
* `1 <= x <= 9`: move forward `x` units

Some of the grid squares are obstacles. 

The `i`-th obstacle is at grid point `(obstacles[i][0], obstacles[i][1])`

If the robot would try to move onto them, the robot stays on the previous grid square instead \(but still continues following the rest of the route.\)

Return the **square** of the maximum Euclidean distance that the robot will be from the origin.

**Example 1:**

```text
Input: commands = [4,-1,3], obstacles = []
Output: 25
Explanation: robot will go to (3, 4)
```

**Example 2:**

```text
Input: commands = [4,-1,4,-2,4], obstacles = [[2,4]]
Output: 65
Explanation: robot will be stuck at (1, 4) before turning left and going to (1, 8)
```

**Note:**

1. `0 <= commands.length <= 10000`
2. `0 <= obstacles.length <= 10000`
3. `-30000 <= obstacle[i][0] <= 30000`
4. `-30000 <= obstacle[i][1] <= 30000`
5. The answer is guaranteed to be less than `2 ^ 31`.

### Analysis

According to the problem description:

**Method I: simulation**

* initial position of the robot is at \(0,0\)  and faces north;
* if `command = -1`, turn right;
* if `command = -2`, turn left;
* if it is positive integers, move forward by current number of steps;
* if there is obstacle long the path, stop before the obstacle and continue with the next command;
* calculate the euclidean distance of its final position to the origin.

The key to solve this problem is to simulate the steps listed above and check for each step if it meets an obstacle.

**Key points:** 

* **have to use set\(\) to remove duplicates in obstacles! Otherwise it will get TLE error.**
*  **-2: turn 90 degrees to the left ——** `dir = (dir -1)%4`**;** 
*  **-1: turn 90 degrees to the right ——`dir = (dir + 1)%4`;** 

**Method II: simulation**

The idea is to create an array to store `up`, `right`, `down` and `left`. Then through a traversal record  the direction the robot is facing \(that is, take  **the mode of** 4\).

**Method III: use dictionary in the simulation**

As for the right and left turns, it is actually to change the orientation of the robot:  

* At first, the robot **faces** `north,` if it turns right , then faces `east,` and a left turn  results in facing `west`. 
* Different orientations mean that the coordinate will be updated differently.

  * If it faces `north`, `x` does not change and `y` increases; 
  * if it faces `south`, `x` does not move and `y` decreases; 
  * if it faces `west`, `x` decreases and `y` does not move; 
  * if it faces `east`, `x` increases and y does not move;
  * that is, each time you perform a movement operation other than the left-to-right turn \(adjusting the direction\), you need to know the direction of the robot. Go forward when you know the direction, and don’t move forward when you encounter obstacles in front of you. End this action and start the next command.

  The hard part is find a way to express moving direction. Here, we can use a nested dictionary: 

  * if current direction is north, then by turning left or right, we may face left or right;
  * if current direction is south, then by turning left or right, we may face right or left;
  * if current direction is east/right, by turning left or right, we may face north or south;
  * if current direction is west/left, by turning left or right, we may face south or north.

### Solution

{% tabs %}
{% tab title="simulation I" %}
```python
class Solution(object):
    def robotSim(self, commands, obstacles):
        """
        :type commands: List[int]
        :type obstacles: List[List[int]]
        :rtype: int
        """
        # use x to represent x-axis, y for y-axis
        dx = [0, 1, 0, -1] # move right and left
        dy = [1, 0, -1, 0] # move upward and downward 
        dir = 0 # direction
        res = 0 # final result
        x = y = 0 # initial position
        
        for cmd in commands:
             if cmd == -1: #turn right 
                 dir = (dir + 1) % 4
             if cmd == -2: #turn left
                 dir = (dir - 1) % 4
             else:
                 for k in range(cmd):
                     if [x + dx[dir], y+dy[dir]] not in obstacles:
                         x += dx[dir]
                         y += dy[dir]
                         res = max(res, x*x + y*y)
        return res 
```
{% endtab %}

{% tab title="simulation II" %}
```python
class Solution(object):
    def robotSim(self, commands, obstacles):
        """
        :type commands: List[int]
        :type obstacles: List[List[int]]
        :rtype: int
        """
        d = [(0,1), (1,0), (0,-1), (-1, 0)]
        res = 0
        direc = 0
        x, y = 0, 0
        ob = set(map(tuple, obstacles))
        for cmd in commands:
            if cmd == -1:
                direc += 1
            elif cmd == -2:
                direc -= 1
            else:
                for i in range(1, cmd+1):
                    x += d[direc%4][0]
                    y += d[direc%4][1]
                    if (x, y) in ob:
                        break
                    
            res = max(res, x**2 + y**2)
        return res       
```

>
{% endtab %}

{% tab title="Use dictionary" %}
```python
class Solution(object):
    def robotSim(self, commands, obstacles):
        """
        :type commands: List[int]
        :type obstacles: List[List[int]]
        :rtype: int
        """
        directions = {'up':  {0:[0,1], -1:'right', -2:'left'},
                      'down': {0:[0,-1], -1:'left', -2:'right'},
                      'left': {0:[-1,0], -1:'up', -2:'down'},
                      'right': {0:[1,0], -1:'down', -2:'up'}
                      }
        obstaclesSet = set(map(tuple, obstacles))
        
        curr_dir = 'up' # current direction
        coord = [0,0] # current coordinates
        res = 0
        
        for cmd in commands:
            if cmd < 0:
                curr_dir = directions[curr_dir][cmd]
            else:
                for i in range(1, cmd+1):
                    x, y = coord[0], coord[1]
                    x += directions[curr_dir][0][0]
                    y += directions[curr_dir][0][1]
                    if (x, y) in obstaclesSet:
                        break
                    coord = [x, y]
                res = max(res, coord[0]**2 + coord[1]**2)
        return res
        
    #another way treat the obstacle encounter problem see method II
                                    
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def robotSim(self, commands, obstacles):
        """
        :type commands: List[int]
        :type obstacles: List[List[int]]
        :rtype: int
        """
```
{% endtab %}

{% tab title="" %}
```python
class Solution(object):
    def robotSim(self, commands, obstacles):
        """
        :type commands: List[int]
        :type obstacles: List[List[int]]
        :rtype: int
        """
        
```
{% endtab %}
{% endtabs %}

### References

