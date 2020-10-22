---
title: "Find All Duplicates Array"
date: 2020-10-21T18:56:19-04:00
draft: false
---

# Find All Duplicates in an Array
## Description
Given an array of integers, 1 ≤ a[i] ≤ n (n = size of array), some elements appear twice and others appear once.

Find all the elements that appear twice in this array.

Could you do it without extra space and in O(n) runtime?

```
Input:
[4,3,2,7,8,2,3,1]

Output:
[2,3]
```

## Solution
This is inspired by finding duplicates in an array with no extra space and O(N) runtime.

For the brute force solution, it's quite easy by using hashmap or set to check for duplicates. A nice trick we can use is that each value of the array is constrained by the length of the array. So we can reuse the input array.

As we iterate through the array, we find the index using the value of the current index, i.e `newIdx = nums[i] - 1`. We check if that value has been negated before. If so, the current value must be duplicate. Otherwise, it's not



