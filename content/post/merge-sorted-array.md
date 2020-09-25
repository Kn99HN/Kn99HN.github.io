---
title: "Merge Sorted Array"
date: 2020-09-25T18:43:58-04:00
draft: false
---

# Merge Sorted Array

## Description
Given two sorted integer arrays nums1 and nums2, merge nums2 into nums1 as one sorted array.

Note:

    The number of elements initialized in nums1 and nums2 are m and n respectively.
    You may assume that nums1 has enough space (size that is equal to m + n) to hold additional elements from nums2.

```
Input:
nums1 = [1,2,3,0,0,0], m = 3
nums2 = [2,5,6],       n = 3

Output: [1,2,2,3,5,6]
```

## Solution
Usually with merge sorted array, I often compare the first 2 elements. Therefore, this question
certainly throw me off since I have to deal with in-place merge sort rather than being able to
allocate for new space.

My first thought was that, we can shift all the elements in nums1 by 1 if `nums1[i] > nums2[i]`.
However, this is not optimal enough. Therefore, we look at the arrays in reverse, we notice
that `nums1` and `nums2` are sorted. Therefore, the last element of the 2 array will determine
which values goes to the empty spot in `nums1`. We iterate the 2 array backward rather than forward
with 3 pointers `tail1=m-1`, `tail2=n-1`, `finished=m+n-1`. The extra can be filled with another
while loop

