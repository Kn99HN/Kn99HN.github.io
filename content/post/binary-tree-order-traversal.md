---
title: "Binary Tree Order Traversal"
date: 2020-09-22T23:46:40-04:00
draft: false
---

# Description
## Desciption
Given a binary tree, return the level order traversal of its nodes' values. (ie, from left to right, level by level).

For example:
Given binary tree [3,9,20,null,null,15,7]

## Solution
We use an iterative approach to the problem and use a queue as our main data structure. We then have nested loop, the outer handle the queue logic while the inner loop handle the popping and adding logic.

