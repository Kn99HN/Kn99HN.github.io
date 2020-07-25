---
title: "Climbing Stairs"
date: 2020-07-25T15:21:33-04:00
draft: false
---

# Climbing Stairs

## Description

You are climbing a stair case. It takes n steps to reach to the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

```
Input: 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

```
Input: 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```
## Solution

The most straightforward way to look at this problem is that we have a few cases. If n <= 2, we know that there are always n ways to climb the stairs. If n > 2, then we need to recurse on n - 1 and n - 2. However, this straightforward solution will not work since it would take exponential running time for large enough value.

We then use dynamic programming, which is a fancy word for memoization. Yeah, memoization not memorization. Rather, it is a word play, I believe, of memory and memorization. I used to be a bit scared of DP. So I would often find the solution before even attempting to solve the problem.

But after Dr. Shoup's Algorithm class, I am a bit more comfortable with it or so I think. So might approach is using a helper function with a dictionary `cache` to store the already computed value.

As we recurse using `n-1` and `n-2`, we are aware that there are lots of repeated value. So we store this as `cache[n]=helper(n-1) + helper(n-2)`. And at the end, we `return cache[n]`. We also check if n is already a key in `cache`, if so, the value is already computed.

