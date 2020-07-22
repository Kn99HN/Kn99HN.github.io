---
title: "Maximum Product Subarray"
date: 2020-07-21T21:56:34-04:00
draft: false
---

# Maximum Product Subarray

## Description

Given an integer array nums, find the contiguous subarray within an array (containing at least one number) which has the largest product.

```
Input: [2,3,-2,4]
Output: 6
Explanation: [2,3] has the largest product 6.
```

## Solution

At first, I wonder why the problem is listed as `Medium` on leetcode since it is
quite similar to maximum sum array. However, I soon found out that a similar approach to the sum array problem will not be sufficient. 

This is due to the fact that product contains negative value so we will not find product of a continuous array because using only one temp value can only record
the maximum value and skip over negative value. 

So, we will have two values `max_val` and `min_val`. We use `max_val` to store
the max of `max_val` * the value of current index i, `min_val` * the value
of the current index i, or the value of current index i. `min_val` is the 
calculated similarly. This is done to ensure that negative value is never
skipped over.
