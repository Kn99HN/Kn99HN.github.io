---
title: "Number of Islands"
date: 2020-08-20T12:46:36-04:00
draft: False
---

# Number of Islands

## Description
Given a 2d grid map of '1's (land) and '0's (water), count the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

## Solution
For these problem, it often requires backtracking as well as depth first search. We created a `visited` 2D array to keep track of pair `i,j` that we have visited. We then visited each index `i,j` in the matrix. If the current index `i,j` is 1, we increment the counter. We also explore starting at each index `i,j`. 

We take all four direction up, down, left and right on each pair `i,j`. Additionally, we also set the `visited[i][j]=True` on each recursive calls. Hence, we avoid stack overflow problem. We also set each index i,j to be 0 on each recursive calls as we have already counted the island branching from the starting index. Hence, we don't want to double count. Our base case would be an out of range `i` or `j` and also if `visited[i][j] == True` or `visited[i][j] == '0'`.

