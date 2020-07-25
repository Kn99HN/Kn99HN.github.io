---
title: "Three Sum"
date: 2020-07-24T21:40:46-04:00
draft: false
---

# Three Sum

## Description

Given an array nums of n integers, are there elements a, b, c in nums such that a + b + c = 0? Find all unique triplets in the array which gives the sum of zero.

```
Given array nums = [-1, 0, 1, 2, -1, -4],

A solution set is:
[
  [-1, 0, 1],
  [-1, -1, 2]
]
```

## Solution
Three sum is the more advanced level of two sum problem. The approach is similar. As we iterate through the list, we lock value at index `i` and solve the two sum problem from there. 

To speed up the process, we sort the list to make it easy to search. We have three pointers, `first` which is the current index `i`, `second` is `i+1` and `third` is `len(nums) - 1`. Using a nested for loops, we find the triplets that sum to 0. If the sum of all three values is greater than 0, we know that the last value, which is now the greater one, must be too large. Similarly, if the sum is smaller than 0, we must increment the `second` value.

Some edge cases we must take care of is that, we don't want duplicate triplets. Hence, if two values next to each other are the same, then we can skip it.

Eventually, if all values are 0, then we add the output to the list.
