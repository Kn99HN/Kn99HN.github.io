---
title: "House Robber"
date: 2020-07-27T22:01:30-04:00
draft: false
---

# Housr Robber

## Description

You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security system connected and it will automatically contact the police if two adjacent houses were broken into on the same night.

Given a list of non-negative integers representing the amount of money of each house, determine the maximum amount of money you can rob tonight without alerting the police.

```
Input: nums = [1,2,3,1]
Output: 4
Explanation: Rob house 1 (money = 1) and then rob house 3 (money = 3).
             Total amount you can rob = 1 + 3 = 4.
```

## Solution
I tried my hand at coin changing problem. Welp, it didn't really go as planned. So I worked on house robber instead. It's a bit easier. 

The concept is similar to other DP easy questions. We have two choices, either take the current value at the index and move two steps behind or take the value at one step behind and forget about the current value.

After this, it's fairly easy to write a recursive function to solve the problem. We then find the max of the two values above.

However, since this will be exponential running time, we want to MEMOIZE!!!!! I prefer using dictionary. We store the max value at the index. It is easy then!

