# 1. Two Sum

## **Problem statement**

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have _**exactly**_ one solution, and you may not use the _same_ element twice.

## **Example:** 

Given nums = \[2, 7, 11, 15\], target = 9,

Because nums\[0\] + nums\[1\] = 2 + 7 = 9, return \[0, 1\].

## Solution 1

Brute force

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i in range(len(nums)-1):
            for j in range(i+1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]
```

**Time complexity : O\(n^2\)**

**Space complexity: O\(1\)**

## Solution 2

One-pass hash table

```python
class Solution(object):
    def woSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        d = {}
        for i in range(len(nums)):
            if target - nums[i] in d.keys():
                return [i, d[target - nums[i]]]
            else: 
                d[nums[i]] = i
```



  


