---
title: "Wiggle Sort"
date: 2020-09-30T12:54:49-04:00
draft: false
---

# Wiggle Sort
## Description
Given an unsorted array nums, reorder it in-place such that nums[0] <= nums[1] >= nums[2] <= nums[3]....

```
Example:
Input: nums = [3,5,2,1,6,4]
Output: One possible answer is [3,5,1,6,2,4]
```

## Solution
Albert actually asks me this question last year. I recall frozen toward the question, I didn't know
where to start. However, after thinking about it a bit. We have a few options:

1. The brute-force and straightforward coming to my mind are:
- We only care about a triplets `a,b,c` such that `a <= b >= c`. That's it.
- We then sort the list
- We ignore the first value and last if length of list is even. Otherwise, we also count the last value in the pair
when we traverse
- We swap `i and i + 1` and increment by 2 for both.

=> Runtime O(n*log(n))

2. The second approach which is more efficient:
- First we iterate through the list.
- We check for 2 cases:
- First, if the index is odd, if `the previous value >= current value`, we will swap them.
- Otherwise, if the  index is even, if `the previous value <= current value`, we will swap them.
- This will give us a valid array since we only and always
care about a triplet of `a,b,c` such that `a <= b >= c`. Nothing else!

=> Runtime: O(n)



