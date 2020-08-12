---
title: "Unique Paths"
date: 2020-08-11T21:34:56-04:00
draft: false
---

# Unique Paths

## Description
A robot is located at the top-left corner of a m x n grid (marked 'Start' in the diagram below).

The robot can only move either down or right at any point in time. The robot is trying to reach the bottom-right corner of the grid (marked 'Finish' in the diagram below).

How many possible unique paths are there?

```
Input: m = 3, n = 2
Output: 3
Explanation:
From the top-left corner, there are a total of 3 ways to reach the bottom-right corner:
1. Right -> Right -> Down
2. Right -> Down -> Right
3. Down -> Right -> Right
```

## Solution
In my opinion, this is a more backtracking problem than a dynamic programming problem. However, it is a DP one because we do have to memoize. We start at `x=0` and `y=0`, end at `x=m-1` and `y=n-1`. So we will need to check for each step. 

We can either make one step at a time, either down or right. Hence, we advance each x by 1 and y by 1. At the end, if we go out of bound, we are sure the robot is outside of the board. Otherwise, if it reaches the end, it must be a valid path. We then use a dictionary as the cache and key as (x,y).


