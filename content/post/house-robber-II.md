---
title: "House Robber II"
date: 2020-07-29T21:48:13-04:00
draft: false
---

# House Robber II

## Description
You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed. All houses at this place are arranged in a circle. That means the first house is the neighbor of the last one. Meanwhile, adjacent houses have security system connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight without alerting the police.

```
Input: [2,3,2]
Output: 3
Explanation: You cannot rob house 1 (money = 2) and then rob house 3 (money = 2), because they are adjacent houses.
```

## Solution
So this is the extension of house robber problem. The only difference is that now, all the houses are in circular. Hence, we cannot take values from pair nums[0]-nums[n - 1].

At first, I thought the approach is similar. However, I learn that we can't really apply all of the logic from the first problem to this problem. After all, it is a harder modification. Luckily, for this problem, we don't have to change much. 

We keep the helper function similar to a normal house robber function with memoization. We then pass in 2 params, `end_pt` and `idx`. `idx` is used similarly, decremented by 1 and 2. However, we used `end_pt` as the values for our stopping point. 

In the main function, we start at the two locations, `len(nums) - 1` and `len(nums) - 2`. We do this because the array is circular. Hence, by starting and stopping at different points, we avoid robbing the illegal pairs. We have two options:
- Start at `len(nums) - 2` and end at `0`
- Start at `len(nums) - 1` and end at `1`

The problem then become [House Robber](https://khanhng.com/post/house-robber/). This problem shows me that, though a problem can be modified, we must keep an open mind and approach it differently. Sometimes, we can get stuck on an approach and don't really change it. So we must keep an open mind!