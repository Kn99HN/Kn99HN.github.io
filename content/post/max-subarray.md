---
title: "Max Subarray"
date: 2020-07-18T21:17:26-04:00
draft: false
---

# Max Subarray

## Description
Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

```
Input: [-2,1,-3,4,-1,2,1,-5,4],
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

## Solution

We keeps track of two variables, local max and global max. We argue that the local maximum value is
either the value from i, ..... j - 1 or the value at index j. Then the global max is the maximum of
the current local max and the global max value. 

By doing this, we can find the maximum sum of the subarray because the local max will only account
for a continuous stream of values from index i,..., j - 1 or restarting the local max at index j.