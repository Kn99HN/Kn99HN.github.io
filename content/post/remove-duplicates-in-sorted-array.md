---
title: "Remove Duplicates in Sorted Array"
date: 2020-09-26T12:29:00-04:00
draft: false
---

# Remove Duplicates from Sorted Array
## Description
Given a sorted array nums, remove the duplicates in-place such that each element appears only once and returns the new length.

Do not allocate extra space for another array, you must do this by modifying the input array in-place with O(1) extra memory.

```
Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.
```

## Solution
Sometimes, I take extra space for granted. The easy way out would
be using a set for O(1) insertion and find. Therefore, it certainly throws
me off guard for doing it inplace. However, luckily, the array is sorted.

Therefore, our approach will use 2 pointers. One to keep track of the `prev`
and one keep track of the `curr`. We iterate through the array. If `nums[prev]=nums[curr]`,
we will increment curr and keep looking. However, if we found 2 elements that are different,
replace `nums[prev]` with `nums[curr]`. When visualizing, it is actually quite similar
to sliding window!



