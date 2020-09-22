---
title: "Maximum Depth Binary Tree"
date: 2020-09-21T22:28:19-04:00
draft: false
---

# Maximum Depth Binary Tree

## Description
Given a binary tree, find its maximum depth.

The maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.

Note: A leaf is a node with no children.
```
Given binary tree [3,9,20,null,null,15,7],
-> Depth = 3
```

## Solution
We recurse on the root node's children and increment a counter. Eventually, we return the max of the 2.



