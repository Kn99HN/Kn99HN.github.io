---
title: "Find the Duplicate Number"
date: 2020-10-27T11:21:25-04:00
draft: false
---

# Find the dupplicate number
## Description
Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.

There is only one duplicate number in nums, return this duplicate number.

Follow-ups:

    How can we prove that at least one duplicate number must exist in nums? 
    Can you solve the problem without modifying the array nums?
    Can you solve the problem using only constant, O(1) extra space?
    Can you solve the problem with runtime complexity less than O(n2)?

```
Input: nums = [1,3,4,2,2]
Output: 2
```

## Solution
There are a few that we can solve with:

### First Approach
Either use a set which takes up more space or modify the array itself.
- We notice that the values is in range [1, n + 1] so we can reuse the values as the indexing for the array.
- Everytime, we will modify `nums[nums[i]] to be negative`, indicating that the values has been marked as visited.
- If ``nums[nums[i]] < 0`, we know that there is a duplicate and we return the absolute value of it.

### Second Approach
Using Floyd's algorithm in finding cycle in linkedlist, we can avoid modify the array in place and also keep run time of O(n).
- We have a fast and slow pointer. We will use these 2 to find the intersection point. The fast will move twice as fast as the slow. Eventually, they will come to a stop.
- We reset the speed of slow and fast to be the same. Eventually, we traverse them similarly, then we will get the entrance of the cycle.



