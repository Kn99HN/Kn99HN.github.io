---
title: "Binary Tree Max Path Sum"
date: 2020-09-28T12:25:28-04:00
draft: false
---

# Binary Tree Max Path Sum
## Description
Given a non-empty binary tree, find the maximum path sum.

For this problem, a path is defined as any sequence of nodes from some starting node to any node in the tree along the parent-child connections. The path must contain at least one node and does not need to go through the root.

```
Input: [1,2,3]

       1
      / \
     2   3

Output: 6
```

## Solution
We initalize a dummy variable called `maxVal`. As we recurse on the tree, we traverse the left
and the right subtree. We take the max of each subtree against 0. We know that if we receive
a negative number, it would bring our value down.

We then update `maxVal=max(maxVal, left + right + root.val)`, which is to calculate the max
path sum at the current node. However, we will return `max(left, right) + root.val` since at
each leaf node, we should only return the `max of either side + root.val`.

