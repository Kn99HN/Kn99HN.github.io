---
title: "Set Matrix Zeroes"
date: 2020-09-08T21:16:16-04:00
draft: false
---

# Set Matrix Zeroes

## Description
Given an m x n matrix. If an element is 0, set its entire row and column to 0. Do it in-place.

Follow up:

    A straight forward solution using O(mn) space is probably a bad idea.
    A simple improvement uses O(m + n) space, but still not the best solution.
    Could you devise a constant space solution?


## Solution
Using a space complexity of O(mn) is a bad idea since most of the time, we only
need to change the `matrix[i][j]` to 0 for given i or j. A better solution 
would be using 2 sets and storing i and j if the `matrix[i][j]==0`. Then, we
iterate again over the matrix and check each i or j to set them to be 0. 

An in-place solution with O(1) space complexity would be using the array itself
as our cache. We first iterate over the matrix, for every row and column, we
modify the first value of each row and column to be the flag itself. We then iterate
over the matrix again, checking for these flags, if it is currently 0, set `matrix[i][j] = 0`.
Otherwise, continue. We also need to be careful of edge cases when first row or
first column contains 0. Therefore, we treat them as separate.