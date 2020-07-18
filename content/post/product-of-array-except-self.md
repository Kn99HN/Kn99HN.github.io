---
title: "Product of Array Except Self"
date: 2020-07-17T22:15:25-04:00
draft: false
---

# Product of array except self

Given an array nums of n integers where n > 1,  return an array output such that output[i] is equal to the product of all the elements of nums except nums[i].

## Example:
```
Input:  [1,2,3,4]
Output: [24,12,8,6]
```

## Solution
We notice that we can do two passes along the array to form the product output. 
We create 2 arrays, left and right. We notice that for the current index i,
it is formed as a product of the original array at index i - 1, and the 
previous value at index i - 1 of the new array. Similarly, for the current
index i, it is formed as a product of the value of the original array
at index i + 1, and the value of the output array at index i + 1.

This is true because, the product of the value at index i is formed as
the product of values at other indices other than i. Therefore, it
is formed by all the values such as i - 1, i - 2, ..., i - j. Similarly,
it is also formed as values of i + 1, i + 2, ...., i + j. 

For this reasoning, we can reason similarly with an induction proof is
that the value at index i in the output array is the product of
the value at index i - 1 of the original array and the value of the
output array at index i - 1. Here, the value of the ouput array at
index i - 1 is the product of all the values before it.


