---
title: "Swap Zeroes"
date: 2020-09-25T09:39:11-04:00
draft: false
---

# Swap Zeroes
## Description
Given an array nums, write a function to move all 0's to the end of it while maintaining the relative order of the non-zero elements.

```
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

## Solution
There are a few approaches that we can take:
1, Use an additional array to add non-zero elements to the list. And we
add all the zero at the end.

2, Use 2 pointers, `lastFound` and interating pointers. We iterate
the array. If we find a non-zero element, we can swap the value
at lastFound and current index. It would keep order of the non-zero element
while having a low swap operations

