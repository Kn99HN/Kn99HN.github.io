---
title: "Search in Rotated Sorted Array"
date: 2020-07-23T21:46:37-04:00
draft: false
---

# Search in Rotated Sorted Array

## Description 

Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.

(i.e., [0,1,2,4,5,6,7] might become [4,5,6,7,0,1,2]).

You are given a target value to search. If found in the array return its index, otherwise return -1.

You may assume no duplicate exists in the array.

Your algorithm's runtime complexity must be in the order of O(log n).

```
Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
```


```
Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
```

## Solution
This is the modified or follow up question from finding minimum in rotated sorted array. No we have one more variant to care about, which is the target value. We then must find the index of the target value. 

The approach, however, can be quite similar. We use two pointers, `low` and `high`. We find the middle index, `mid`. 
We compare these value to each other. There are a two scenarios that can happen:

1. The `mid` value is greater than the `low` value, meaning that from low to mid, there is an ordered sequence. 
2. The `mid` value is smaller than the `low` value, meaning that from mid to high, there is an ordered sequence.

However, since we must find the `target` value, we have a few more scenarios to consider within the first two. 

In scenario 1, we have:

1. If `target` is smaller than the `mid` value and `target` is 
greater than the `low` value, then the `target` falls into the ordered sequence on the left.
2. Otherwise, it must be on the right.

In scenario 2, we have:
1. If `target` is greater than the `mid` value and `target` is smaller than the high value, then the `target` falls into the ordered sequence on the right.
2. Otherwise, it must be on the left.

At the end of the while loop, we return -1 since the loop ends, indicating no value can be found that is the target.


