---
title: "Jump Game"
date: 2020-08-13T21:11:33-04:00
draft: false
---

# Jump Game
## Description
Given an array of non-negative integers, you are initially positioned at the first index of the array. Each element in the array represents your maximum jump length at that position. Determine if you are able to reach the last index. For example: A = [2,3,1,1,4], return true. A = [3,2,1,0,4], return false.

## Solution
We use a greedy approach to the problem. We know that the current index represents the maximum length we can skip to in the array.

Hence, if `nums[i] + curr_max >= last index in the array`, then there must be a path to the end of the array. However, if the current index is less than the length and it is zero, it will be false. We only need to loop through the array once to keep track of the max value to ensure it will go out of bound, if so return true. If at the end of the loop, there is no way to get to the end, the answer must be false   

