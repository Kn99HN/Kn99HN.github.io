---
title: "Find Min in Rotated Sorted Array"
date: 2020-10-12T09:36:54-04:00
draft: false
---

# Find Min in Rotated Sorted Array
## Description
Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.

(i.e.,  [0,1,2,4,5,6,7] might become  [4,5,6,7,0,1,2]).

Find the minimum element.

The array may contain duplicates.

```
Input: [1,3,5]
Output: 1
```

## Solution
This is pretty similar to find min in rotated sorted array. One caveat is that there might be duplicates in the array.

So we identify 3 cases/conditions:
1. If `mid < high`, then the array is sorted normally. We move
our `high = mid`. Hence, the min must be on LHS
2. If `mid > high`, then the array is rotated and sorted. We move our `low = mid`. Hence, the min must be on the RHS.
3. If `mid == high`, we will decrement the `high -= 1` since we know that the array can either be rotated or sorted normally. In the case it's the same, our min might be on the RHS, so we don't move our `low` or `high` to the `mid`. Rather, we decrement the counter to ensure we don't miss the value.

=> Runtime: O(n) with n being the number of values in the array. Best case O(logn)

