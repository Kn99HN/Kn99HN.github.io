---
title: "Length of Increasing Sub"
date: 2020-08-03T21:18:33-04:00
draft: false
---

# Length of Increasing Subsequence

## Description
Given an unsorted array of integers, find the length of longest increasing subsequence.

```
Input: [10,9,2,5,3,7,101,18]
Output: 4 
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
```

## Solution
This problem is similar to longest common subsequence working with strings. For each current value, we keep track of the previous index. We make a comparison of the `current index` and `previous index`. If `current index` value is less than the value at `previous index`, we increment the counter by 1. 
If not, we skip the current index while keeping `previous index`. 

We then take the maximum of the two outcomes. At the end, for memoization, we use a 2D array, indexed by `current index` and `previous index`. Then we just have to check if these values have been calculated. If so, return it. 