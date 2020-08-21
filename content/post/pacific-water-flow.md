---
title: "Pacific Atlanti Water Flow"
date: 2020-08-21T13:34:24-04:00
draft: false
---

# Pacific Atlantic Water Flow

## Description

Given an m x n matrix of non-negative integers representing the height of each unit cell in a continent, the "Pacific ocean" touches the left and top edges of the matrix and the "Atlantic ocean" touches the right and bottom edges.

Water can only flow in four directions (up, down, left, or right) from a cell to another one with height equal or lower.

Find the list of grid coordinates where water can flow to both the Pacific and Atlantic ocean.

```
Given the following 5x5 matrix:

  Pacific ~   ~   ~   ~   ~ 
       ~  1   2   2   3  (5) *
       ~  3   2   3  (4) (4) *
       ~  2   4  (5)  3   1  *
       ~ (6) (7)  1   4   5  *
       ~ (5)  1   1   2   4  *
          *   *   *   *   * Atlantic

Return:

[[0, 4], [1, 3], [1, 4], [2, 2], [3, 0], [3, 1], [4, 0]] (positions with parentheses in above matrix).
```

## Solution 
I struggled with this problem at first. I use the usual approach of DFS but it didn't seem to work. However, after reading over the solution, I had a better understanding why a better approach is needed. 

We create two 2D array, `atl` and `pac` to keep track of atlantic and pacific ocean side. We notice that the surrounding square of the matrix are all touching the ocean. Hence, instead of iterating through all of the cells in the matrix, we iterate rows and column separately. By doing so, we start from the border and explore the inner land instead of the other way around, which was what I initally planned to do. One lesson from this problem I notice is that I need to look at the problem differently. Even though it's a DFS and matrix exploration problem, it's better to keep track of the previous value and explore from the border inwards instead of the other way around. 

In the DFS function, we keep track of the previous value and return if the current value is less than the previous value. We also keep track of the visited node by setting `ocean[i][j]=True` for each recursive calls. 