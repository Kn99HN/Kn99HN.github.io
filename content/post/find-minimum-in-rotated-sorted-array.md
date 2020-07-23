---
title: "Find Minimum in Rotated Sorted Array"
date: 2020-07-22T21:06:57-04:00
draft: false
---

# Find Minimum in Rotated Sorted Array

## Description

Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.

(i.e.,  [0,1,2,4,5,6,7] might become  [4,5,6,7,0,1,2]).

Find the minimum element.

You may assume no duplicate exists in the array.

```
Input: [3,4,5,1,2] 
Output: 1
```

## Solution
This question funnily enough got me rejected from Microsoft Explore. On the day of the onsite, 
I never did an inch of leetcode so the question came us a shock to me. I eventually found out
the question while preparing for the other technical interviews. 

This is a modified version of binary search. We will have a low and high pointer, finding
the middle point as we go. There are 3 scenarios:
1. The middle value is greater than both low and high value.
2. The middle value is smaller than both low and high value.
3. The middle value is in its natural order, greater than low value and smaller than high value. 

Each time, we calculate the middle index and its value. We check if there is a drop in the value
at index i + 1. If there is, it indicates that value at i + 1 is the minimum value in the array. Otherwise, if we fall
into scenario 1, we will move the low pointer to mid pointer.
we do conversely in scenario 2. 

Eventually, if the loop ends, we know that low and high falls 
into the same index. Hence, in that case, the value at that
index will be the min.


