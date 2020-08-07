---
title: "Combination Sum IV"
date: 2020-08-06T21:48:54-04:00
draft: false
---

# Combination Sum IV

## Description
Given an integer array with all positive numbers and no duplicates, find the number of possible combinations that add up to a positive integer target.

```
nums = [1, 2, 3]
target = 4

The possible combination ways are:
(1, 1, 1, 1)
(1, 1, 2)
(1, 2, 1)
(1, 3)
(2, 1, 1)
(2, 2)
(3, 1)

Note that different sequences are counted as different combinations.

Therefore the output is 7.
```

## Solution
This is similar to the Coin Change problem. However, instead of finding unique combination, we are counting number of ordered list. We know that if target is 0, then there is a combination found. Otherwise, if `target` greater than current `num`, indicating that the current value is involved in the combination counting.

We then subtract `target` from current `num` to achieve the counter we need.

