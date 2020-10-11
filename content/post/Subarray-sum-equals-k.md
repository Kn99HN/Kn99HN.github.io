---
title: "Subarray Sum Equals K"
date: 2020-10-10T22:32:08-04:00
draft: false
---

# Subarray Sum Equals K
## Description
Given an array of integers and an integer k, you need to find the total number of continuous subarrays whose sum equals to k.

```
Input:nums = [1,1,1], k = 2
Output: 2
```

## Solution
We can solve by using a few approaches. Brute force solution requires O(n^2) with a nested for loop and check if the sum == k.

A better solution is to use a HashMap. We adding cumulative into the hashmap with a counter of how many times the sum appears. We then just check if `sum - k` is in the hashmap, if so add it to counter. 

This will work because we are accumulate the sum and we know that we need `a + b = k` => `a - k = b` => `sum - k = appeared sum in hashmap`. If the sum appear in the hasmap, increment its counter. We also have add a base case `(0,1)`.

