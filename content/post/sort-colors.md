---
title: "Sort Colors"
date: 2020-10-02T08:40:55-04:00
draft: false
---

# Sort Colors
## Description
Given an array nums with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

Here, we will use the integers 0, 1, and 2 to represent the color red, white, and blue respectively.

Follow up:

    Could you solve this problem without using the library's sort function?
    Could you come up with a one-pass algorithm using only O(1) constant space?

```
Input: nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]
```

## Solution
1. 
- A straightforward and brute force solution would be use 3
integer values to store number of 0, 1 and 2 in the nums array.
- We then can replace all of the number in the array with these counters.

2. 
- A better approach is to use 2 pointers. We would like to shift all 0s to the left and 2s to the right and 1s in the middle. 
- We have 2 pointers acting as our 1s limit, `left` and `right`.
- We iterate through the array. We will handle 3 cases:
- If current value == 0, we swap with our left pointer. We then increment left and increment current value as well.
- If current value == 1, we increment left pointer.
- If current value == 2, we swap with our right pointer and decrement the right pointer. The caveat here is that we don't want to increment current counter like in the first case. This is due to the fact that if both numbers we swap are 2, we would like to swap it with the next right pointer.



