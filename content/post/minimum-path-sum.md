---
title: "Minimum Path Sum"
date: 2020-10-19T22:42:18-04:00
draft: true
---

# Minimum Path Sum
## Description
Given a m x n grid filled with non-negative numbers, find a path from top left to bottom right which minimizes the sum of all numbers along its path.

Note: You can only move either down or right at any point in time.

```
Input:
[
  [1,3,1],
  [1,5,1],
  [4,2,1]
]
Output: 7
Explanation: Because the path 1→3→1→1→1 minimizes the sum.
```

## Solution
Since we already know the start and end node, we can run dfs with memoization so it's pretty straightforward. Otherwise, if we don't know the start and destination node. We can run dijkstra on the 2D array itself.